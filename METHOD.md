# METHOD.md — PDCA-T Technical Reference / Referencia Técnica

> This file is the canonical technical specification of the PDCA-T method.  
> Este archivo es la especificación técnica canónica del método PDCA-T.

---

# 🇬🇧 ENGLISH

## What is PDCA-T?

PDCA-T is an enhancement of the classic Plan-Do-Check-Act (PDCA) management cycle, extended with a mandatory **Test** phase and adapted for AI-assisted software development. It transforms the inherently exploratory nature of AI coding into a systematic, auditable, and reproducible process.

The core insight: **quality is not inspected at the end — it is built into every step.**

## The 8 Phases — Technical Specification

### Phase 1: Planning

**Goal:** Establish unambiguous understanding before writing code.

**Required outputs:**
- One-sentence objective statement
- Explicit scope boundary (IN scope / OUT of scope)
- List of clarifying questions asked and answered
- External dependencies identified (APIs, libraries, services, infrastructure)
- Acceptance criteria defined and agreed upon

**Blocking condition:** Do not advance to Phase 2 if the objective is still ambiguous.

---

### Phase 2: Requirements Analysis

**Goal:** Capture all requirements — functional and non-functional — plus a risk register.

**Required outputs:**

Functional Requirements format:
```
FR-NN: [Description of what the system must do]
  Acceptance: [How to verify it works]
  Priority: Must / Should / Could
```

Non-Functional Requirements format:
```
NFR-NN: [Description of constraint or quality attribute]
  Metric: [Measurable target — e.g. "< 100ms p99"]
  Verification: [How to measure]
```

Risk Register format:
```
RISK-NN: [Description of the risk]
  Probability: High / Medium / Low
  Impact: High / Medium / Low
  Mitigation: [Specific action to reduce or eliminate]
```

---

### Phase 3: Architecture Design

**Goal:** Make architectural decisions explicit and documented before any implementation begins.

**Required outputs:**

**ADR (Architecture Decision Record):**
```
ADR-NN: [Short decision title]
  Context: [Why a decision is needed]
  Decision: [What was decided, in one sentence]
  Alternatives: [What else was considered]
  Consequences: [Positive and negative outcomes]
```

**Interface Contracts** (defined before implementing):
```python
def function_name(
    param1: Type,
    param2: Type = default
) -> ReturnType:
    """
    [One-line summary]

    Args:
        param1: [description, constraints]
        param2: [description, default behavior]

    Returns:
        [description of return value]

    Raises:
        ErrorType: [when this is raised]
    """
    ...  # implementation follows in Phase 4
```

**Module Structure** (chosen before coding):
```
src/
├── domain/          # Pure business logic — no external dependencies allowed
│   ├── models.py    # Entities, value objects, aggregates
│   └── services.py  # Use cases, business rules
├── infrastructure/  # External adapters only (DB, APIs, queues, cache)
│   ├── db/
│   └── external/
└── interfaces/      # Entry points only (HTTP, CLI, events)
    ├── api/
    └── cli/

tests/
├── unit/            # No I/O — domain only
├── integration/     # Real infrastructure, isolated
└── e2e/             # Full flow, real environment
```

---

### Phase 4: Micro-Task Cycle

**Goal:** Implement in small, validated, reversible increments.

**Hard constraint:** ≤ 50 lines per micro-task (excluding tests and docstrings).

**Why 50 lines?**
- Reviewable in < 5 minutes
- Forces single responsibility
- Fully testable in isolation
- Easy to roll back if broken
- Prevents scope accumulation within a task

#### Sub-phase 4.1 — Context Check

Before writing any code:
- Check available skills (`.cursor/skills/`, context files)
- Identify reusable code from Phase 3 contracts
- Confirm interface contract is defined for this task

#### Sub-phase 4.2 — Test First (Mandatory TDD)

Tests are written **before** implementation. Always.

Required test categories for every function:

| Category | Description | Example |
|----------|-------------|---------|
| Happy path | Normal operation with valid input | `test_calculate_vat_standard()` |
| Error case | Validation failure, expected exception | `test_calculate_vat_negative_price_raises()` |
| Edge case | Boundary values, empty, zero, max | `test_calculate_vat_minimum_price()` |
| Security | Input injection, type coercion, overflow | `test_calculate_vat_rejects_float()` |
| Performance | Latency or throughput constraint | `test_bulk_performance()` |

Test naming convention:
```
test_[function]_[scenario]_[expected_outcome]
```

Test structure (Arrange-Act-Assert):
```python
def test_calculate_vat_standard_vat_applied():
    # Arrange
    base_price = Decimal("100.00")
    
    # Act
    result = calculate_vat(base_price)
    
    # Assert
    assert result.vat_amount == Decimal("21.00")
    assert result.total == Decimal("121.00")
```

#### Sub-phase 4.3 — Implementation

Code standards (non-negotiable):

```python
# ✅ CORRECT
from decimal import Decimal
from dataclasses import dataclass
from typing import Optional
import logging

logger = logging.getLogger(__name__)

@dataclass(frozen=True)
class VATResult:
    base: Decimal
    vat_amount: Decimal
    total: Decimal
    currency: str

def calculate_vat(
    base_price: Decimal,
    vat_rate: Decimal = Decimal("0.21"),
    currency: str = "EUR"
) -> VATResult:
    """
    Calculate VAT on a base price.

    Args:
        base_price: Pre-tax price. Must be > 0.
        vat_rate: VAT rate as decimal. Must be in [0, 1].
        currency: ISO 4217 currency code.

    Returns:
        VATResult with base, vat_amount, and total.

    Raises:
        TypeError: If base_price is not Decimal.
        ValueError: If base_price <= 0.
        ValueError: If vat_rate not in [0, 1].
    """
    if not isinstance(base_price, Decimal):
        raise TypeError(f"base_price must be Decimal, got {type(base_price).__name__}")
    if base_price <= Decimal("0"):
        raise ValueError(f"base_price must be positive, got {base_price}")
    if not Decimal("0") <= vat_rate <= Decimal("1"):
        raise ValueError(f"vat_rate must be in [0, 1], got {vat_rate}")

    vat_amount = base_price * vat_rate
    result = VATResult(
        base=base_price,
        vat_amount=vat_amount,
        total=base_price + vat_amount,
        currency=currency
    )
    logger.debug("VAT calculated", extra={"base": str(base_price), "vat": str(vat_amount)})
    return result
```

Prohibited patterns:
```python
# ❌ No type hints
def calculate(price, rate):

# ❌ Float for money
vat = 100.0 * 0.21

# ❌ Hardcoded configuration
VAT_RATE = 0.21  # in source code

# ❌ Bare except
try:
    ...
except:
    pass

# ❌ No validation
def calculate_vat(base_price):
    return base_price * VAT_RATE  # no checks
```

#### Sub-phase 4.4 — Self-Review Checklist

Mandatory before executing tests:

```
CODE QUALITY
  □ Type hints on every parameter and return value
  □ Docstring with Args, Returns, Raises
  □ Single responsibility (one function = one job)
  □ Semantic names (no a, b, x, tmp, data)
  □ No code duplication (DRY)
  □ Consistent abstraction level

SECURITY
  □ Every input validated before use
  □ Outputs sanitized before display or storage
  □ No hardcoded secrets, tokens, or passwords
  □ No sensitive data in log messages
  □ Safe types (Decimal for money, not float)

MAINTAINABILITY
  □ Another developer can understand in < 2 minutes
  □ Errors logged with structured context
  □ No magic numbers (use named constants)
  □ No commented-out code
```

#### Sub-phase 4.5 — Execute and Show Real Results

**MANDATORY:** Show the complete, unedited pytest output. Never summarize.

Required command:
```bash
pytest tests/ -v --cov=src --cov-report=term-missing --tb=short
```

Required output format:
```
tests/unit/test_vat.py::TestVAT::test_happy_path PASSED
tests/unit/test_vat.py::TestVAT::test_error_case PASSED
...

Name                  Stmts   Miss  Cover   Missing
----------------------------------------------------
src/domain/services.py   14      0   100%
----------------------------------------------------
TOTAL                    14      0   100%

N passed in X.XXs
```

**NEVER acceptable:**
- "All tests pass" (without showing output)
- "Coverage is around 99%"
- Showing partial output

#### Sub-phase 4.6 — Coverage Validation

```
IF all tests pass AND coverage ≥ 99%:
    → Advance to next micro-task or Phase 5

IF any test fails:
    → Fix the code (not the test, unless test is wrong)
    → Explain what was wrong and why
    → Re-run from 4.5

IF coverage < 99%:
    → Identify exactly which lines are uncovered (pytest shows them)
    → Add specific tests for uncovered paths
    → Re-run from 4.5

IF 100% is genuinely unreachable (e.g. defensive error handlers):
    → Explain why with pragma: no cover
    → Document in delivery report
```

---

### Phase 5: Integral Validation with Metrics

**Goal:** Comprehensive quality review across five dimensions.

#### Security Checklist (OWASP-aligned)
```
□ No SQL injection surface (parameterized queries only)
□ No command injection surface
□ Input validation on all entry points
□ Output encoding/sanitization before rendering
□ No hardcoded credentials or API keys
□ No sensitive data in logs or error messages
□ Authentication required where applicable
□ Authorization checked per action (RBAC/ABAC)
□ Rate limiting on public endpoints
□ Dependency audit (pip-audit / npm audit)
```

#### Test Metrics (must all be green)
```
□ Total tests: [N] — all accounted for
□ Passed: [N] — 100%
□ Failed: 0 — zero tolerance
□ Skipped: 0 — justify any skips explicitly
□ Coverage: ≥ 99% — enforced by --cov-fail-under=99
□ Test types present: Happy + Error + Edge + Security
□ No tests with only happy paths
```

#### Code Quality Metrics
```
□ Type hint coverage: 100% of public functions
□ Cyclomatic complexity: < 10 per function (radon cc -a -nb src/)
□ Cognitive complexity: < 15 per function
□ No duplication: < 5% (radon / SonarQube)
□ Docstring coverage: 100% of public API
□ No TODO/FIXME in delivered code (register as DEBT-XXX instead)
```

#### Performance Checklist
```
□ No N+1 query patterns
□ Database indexes on all filter/sort fields
□ Pagination on all collection endpoints
□ External call timeouts configured
□ Cache strategy defined for hot data
□ Memory leaks checked (no unbounded collections)
```

#### Architecture Checklist
```
□ No circular imports (check with: python -c "import src")
□ Domain layer has zero external dependencies
□ Infrastructure layer does not contain business logic
□ Interfaces layer does not contain business logic
□ All module dependencies point inward (Clean Architecture)
□ No feature envy (functions that belong in another module)
```

---

### Phase 6: Technical Debt Management

**Goal:** Make all known issues visible, prioritized, and planned.

**Principle:** Unregistered debt is hidden debt. Hidden debt becomes production incidents.

**DEBT-XXX format:**
```
DEBT-XXX: [Short title]
  Type: Technical | Test | Documentation | Architecture | Security | Performance
  Description: [What the problem is and why it exists]
  Impact: High | Medium | Low — [one-line justification]
  Effort: [Estimated hours]
  Priority: High | Medium | Low
  Status: Open | In Progress | Resolved
  Plan: [Specific action — "Implement in v1.1 with exchange rate service"]
  Added: YYYY-MM-DD
```

**Priority rules:**
- **High** → Must be resolved in the next sprint. Blocks quality or security.
- **Medium** → Must be resolved within 2-3 sprints. Impacts maintainability.
- **Low** → Tracked. Planned for a future version. No immediate impact.

---

### Phase 7: Refinement to ≥ 99%

**Goal:** Close all gaps identified in Phase 5 before delivery.

**Mandatory loop:**
```
1. IDENTIFY   What specific metric is below target? (be exact)
2. CLASSIFY   High / Medium / Low priority
3. PLAN       What specific action will fix it?
4. EXECUTE    Implement the fix
5. VERIFY     Re-run the full test suite
6. CONFIRM    Is ≥ 99% achieved on all dimensions?
              YES → advance to Phase 8
              NO  → return to step 1
```

**Hard rule:** Never advance to Phase 8 without ≥ 99% confirmed on all five validation dimensions.

---

### Phase 8: Delivery with Full Report

**Goal:** Document what is being delivered and provide full evidence of quality.

**Required sections (see templates/delivery-report.md for full template):**

1. Implementation summary (2-3 sentences)
2. Test report table (total / passed / failed / coverage / time)
3. Full unedited pytest output
4. Key technical decisions with justifications
5. Technical debt registered during this delivery
6. CI/CD checklist (all items confirmed)
7. Suggested next steps

---

## Absolute Rules

These rules are enforced regardless of context, time pressure, or user request:

| # | Rule | Violation |
|---|------|-----------|
| 1 | Tests written BEFORE implementation | Writing code before tests |
| 2 | Show REAL test output | Summarizing or omitting output |
| 3 | No hardcoded secrets | Any credential in source code |
| 4 | Coverage ≥ 99% before delivery | Delivering below threshold |
| 5 | ADRs for non-trivial decisions | Undocumented architectural choices |
| 6 | All issues registered as DEBT-XXX | Ignoring or hiding known problems |

---

## Quality Targets Reference

| Metric | Target | Enforcement |
|--------|--------|-------------|
| Test coverage | ≥ 99% | `--cov-fail-under=99` in CI |
| Tests failed | 0 | CI fails on any failure |
| Lines per micro-task | ≤ 50 | Manual review |
| Cyclomatic complexity | < 10/fn | `radon cc` in CI |
| Type hint coverage | 100% public | `mypy --strict` in CI |
| Hardcoded secrets | 0 | `bandit` + `gitleaks` in CI |
| Docstring coverage | 100% public | `pydocstyle` in CI |

---

---

# 🇪🇸 ESPAÑOL

## ¿Qué es PDCA-T?

PDCA-T es una mejora del ciclo clásico de gestión Plan-Do-Check-Act (PDCA), extendido con una fase de **Test** obligatoria y adaptado para el desarrollo de software asistido por IA. Transforma la naturaleza inherentemente exploratoria de la codificación con IA en un proceso sistemático, auditable y reproducible.

La premisa central: **la calidad no se inspecciona al final — se construye en cada paso.**

## Las 8 Fases — Especificación Técnica

### Fase 1: Planificación

**Objetivo:** Establecer comprensión inequívoca antes de escribir código.

**Outputs requeridos:**
- Declaración del objetivo en una oración
- Límite de alcance explícito (qué SÍ / qué NO está en el alcance)
- Lista de preguntas de clarificación formuladas y respondidas
- Dependencias externas identificadas (APIs, librerías, servicios, infraestructura)
- Criterios de aceptación definidos y acordados

**Condición de bloqueo:** No avanzar a la Fase 2 si el objetivo aún es ambiguo.

---

### Fase 2: Análisis de Requisitos

**Objetivo:** Capturar todos los requisitos — funcionales y no funcionales — más un registro de riesgos.

**Outputs requeridos:**

Formato de Requisitos Funcionales:
```
RF-NN: [Descripción de lo que el sistema debe hacer]
  Aceptación: [Cómo verificar que funciona]
  Prioridad: Debe / Debería / Podría
```

Formato de Requisitos No Funcionales:
```
RNF-NN: [Descripción de la restricción o atributo de calidad]
  Métrica: [Objetivo medible — ej. "< 100ms p99"]
  Verificación: [Cómo medir]
```

Formato del Registro de Riesgos:
```
RIESGO-NN: [Descripción del riesgo]
  Probabilidad: Alta / Media / Baja
  Impacto: Alto / Medio / Bajo
  Mitigación: [Acción específica para reducir o eliminar]
```

---

### Fase 3: Diseño de Arquitectura

**Objetivo:** Hacer explícitas y documentadas las decisiones arquitectónicas antes de que comience cualquier implementación.

**Outputs requeridos:**

**ADR (Architecture Decision Record):**
```
ADR-NN: [Título corto de la decisión]
  Contexto: [Por qué se necesita una decisión]
  Decisión: [Qué se decidió, en una oración]
  Alternativas: [Qué más se consideró]
  Consecuencias: [Resultados positivos y negativos]
```

**Contratos de Interfaz** (definidos antes de implementar):
```python
def nombre_funcion(
    param1: Tipo,
    param2: Tipo = default
) -> TipoRetorno:
    """
    [Resumen en una línea]

    Args:
        param1: [descripción, restricciones]
        param2: [descripción, comportamiento por defecto]

    Returns:
        [descripción del valor de retorno]

    Raises:
        TipoError: [cuándo se lanza]
    """
    ...  # implementación sigue en Fase 4
```

**Estructura de Módulos** (elegida antes de codificar):
```
src/
├── domain/          # Lógica de negocio pura — sin dependencias externas
│   ├── models.py    # Entidades, value objects, agregados
│   └── services.py  # Casos de uso, reglas de negocio
├── infrastructure/  # Solo adaptadores externos (DB, APIs, colas, caché)
└── interfaces/      # Solo puntos de entrada (HTTP, CLI, eventos)

tests/
├── unit/            # Sin I/O — solo dominio
├── integration/     # Infraestructura real, aislada
└── e2e/             # Flujo completo, entorno real
```

---

### Fase 4: Ciclo de Micro-Tareas

**Objetivo:** Implementar en incrementos pequeños, validados y reversibles.

**Restricción dura:** ≤ 50 líneas por micro-tarea (excluyendo tests y docstrings).

#### Sub-fase 4.2 — Tests Primero (TDD Obligatorio)

Los tests se escriben **antes** de la implementación. Siempre.

Categorías de tests requeridas para cada función:

| Categoría | Descripción | Ejemplo |
|-----------|-------------|---------|
| Happy path | Operación normal con input válido | `test_calculate_vat_standard()` |
| Caso de error | Fallo de validación, excepción esperada | `test_calculate_vat_precio_negativo_lanza()` |
| Caso límite | Valores en frontera, vacío, cero, máximo | `test_calculate_vat_precio_minimo()` |
| Seguridad | Inyección de input, coerción de tipos | `test_calculate_vat_rechaza_float()` |
| Rendimiento | Restricción de latencia o throughput | `test_bulk_rendimiento()` |

#### Sub-fase 4.5 — Ejecutar y Mostrar Resultados Reales

**OBLIGATORIO:** Mostrar el output completo y sin editar de pytest. Nunca resumir.

#### Sub-fase 4.6 — Validación de Cobertura

```
SI todos los tests pasan Y cobertura ≥ 99%:
    → Avanzar a la siguiente micro-tarea o Fase 5

SI algún test falla:
    → Corregir el código (no el test, a menos que el test esté equivocado)
    → Explicar qué estaba mal y por qué
    → Re-ejecutar desde 4.5

SI cobertura < 99%:
    → Identificar exactamente qué líneas no están cubiertas
    → Agregar tests específicos para esos caminos
    → Re-ejecutar desde 4.5
```

---

### Fases 5-8

Ver la sección en inglés para la especificación completa — la lógica es idéntica.

**Resumen:**
- **Fase 5:** Validación en 5 dimensiones: seguridad, tests, calidad de código, rendimiento, arquitectura
- **Fase 6:** Registrar toda deuda conocida en formato DEUDA-XXX con prioridad y plan
- **Fase 7:** Iterar hasta ≥ 99% en todas las métricas — nunca entregar por debajo
- **Fase 8:** Reporte completo con evidencia real de calidad

---

## Reglas Absolutas

| # | Regla | Violación |
|---|-------|-----------|
| 1 | Tests escritos ANTES de la implementación | Escribir código antes de los tests |
| 2 | Mostrar output REAL de tests | Resumir u omitir el output |
| 3 | Sin secretos hardcodeados | Cualquier credencial en el código fuente |
| 4 | Cobertura ≥ 99% antes de la entrega | Entregar por debajo del umbral |
| 5 | ADRs para decisiones no triviales | Elecciones arquitectónicas sin documentar |
| 6 | Todos los problemas como DEUDA-XXX | Ignorar u ocultar problemas conocidos |

---

## Referencia de Objetivos de Calidad

| Métrica | Objetivo | Aplicación |
|---------|----------|------------|
| Cobertura de tests | ≥ 99% | `--cov-fail-under=99` en CI |
| Tests fallidos | 0 | CI falla ante cualquier fallo |
| Líneas por micro-tarea | ≤ 50 | Revisión manual |
| Complejidad ciclomática | < 10/fn | `radon cc` en CI |
| Cobertura de type hints | 100% público | `mypy --strict` en CI |
| Secretos hardcodeados | 0 | `bandit` + `gitleaks` en CI |
