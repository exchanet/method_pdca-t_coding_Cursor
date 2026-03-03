# 🔁 Método PDCA-T — Framework de Calidad para Codificación con IA

> **Una metodología sistemática multi-agente para desarrollo asistido por IA que garantiza ≥99% de cobertura de tests, cero vulnerabilidades, cero bugs en producción y entrega completamente documentada.**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Version](https://img.shields.io/badge/version-3.0.0-blue.svg)]()
[![Agent: Any](https://img.shields.io/badge/agente-cualquiera-green.svg)]()
[![Language: ES/EN](https://img.shields.io/badge/Idioma-ES%2FEN-blue.svg)](./README.md)

**Autor original:** Francisco J. Bernades ([@exchanet](https://github.com/exchanet))  
**Repositorio:** [github.com/exchanet/method_pdca-t_coding](https://github.com/exchanet/method_pdca-t_coding)

---

> ⚠️ **¿Quieres sistemas completos listos para producción?**  
> El Método PDCA-T se ocupa de la calidad, los tests y la validación sistemática.  
> Para arquitectura modular con Admin Panels auto-generados, úsalo junto a **[Method Modular Design](https://github.com/exchanet/method_modular_design)**.  
> *Modular Design construye el sistema correcto. PDCA-T lo construye bien.*

---

## 🎯 ¿Qué hace el Método PDCA-T?

El Método PDCA-T instruye a cualquier agente de IA para seguir un ciclo de calidad riguroso donde:

- ✅ **La arquitectura se diseña antes del código** — ADRs y contratos de interfaz primero
- ✅ **Los tests se escriben antes de la implementación** — TDD estricto, no opcional
- ✅ **Cada micro-tarea ≤ 50 líneas** — enfocada, revisable, responsabilidad única
- ✅ **Cobertura ≥ 99% obligatoria** — exigida antes de cualquier entrega
- ✅ **La deuda técnica se registra** — priorizada, planificada, visible
- ✅ **Cada entrega tiene reporte completo** — tests, decisiones, checklist CI/CD
- ✅ **Funciona con cualquier agente** — Cursor, Windsurf, GitHub Copilot, Claude Code, Claude.ai, ChatGPT, Aider
- ✅ **Funciona con cualquier stack** — Python, Node.js, Go, TypeScript, cualquier lenguaje

---

## 🚀 Inicio Rápido

### Instalación — 3 opciones

**Opción 1 — enet (recomendado)**

[`enet`](https://github.com/exchanet/enet) es el gestor de métodos de exchanet. Detecta tu agente de IA automáticamente e instala el adapter en el lugar correcto.

```bash
npm install -g @exchanet/enet
enet install pdca-t
```

**Opción 2 — enet vía GitHub (sin cuenta npm)**

```bash
npm install -g github:exchanet/enet
enet install pdca-t
```

**Opción 3 — Manual**

Descarga el adapter para tu agente desde la carpeta `adapters/`:

| Agente | Archivo | Ubicación |
|--------|---------|-----------|
| Cursor | `adapters/cursor.md` | `.cursor/rules/method-pdca-t.md` |
| Windsurf | `adapters/windsurf.md` | Añadir al final de `.windsurfrules` |
| GitHub Copilot | `adapters/copilot.md` | `.github/copilot-instructions.md` |
| Claude Code | `adapters/claudecode.md` | `CLAUDE.md` |
| Claude.ai | `adapters/claudeai.md` | Pegar en el system prompt o conversación |
| ChatGPT / GPT-4o | `adapters/openai.md` | Pegar en las instrucciones personalizadas |
| Aider | `adapters/aider.md` | Flag `--system-prompt` o `.aider.conf.yml` |
| Cualquier otro agente | `adapters/generic.md` | Pegar en el contexto de tu agente |

---

## 📖 El Método Explicado

### Por qué funciona PDCA-T

La codificación con IA tradicional omite la validación o la trata como un paso final. PDCA-T **integra el aseguramiento de calidad en cada paso**:

1. **La planificación previene el scope creep** — Objetivos claros antes de una sola línea de código
2. **Arquitectura primero** — Decisiones documentadas antes de comenzar la implementación
3. **TDD por defecto** — Tests escritos antes del código, nunca después
4. **Micro-tareas para mayor enfoque** — ≤ 50 líneas por tarea garantizan profundidad
5. **Validación inmediata detecta errores temprano** — Nunca descubrir bugs en producción
6. **Registro de deuda previene acumulación** — Los problemas conocidos son visibles, no enterrados
7. **Seguridad primero** — Validación de inputs y sanitización de outputs desde el día uno

---

## 🔄 El Ciclo Completo de 8 Fases

```
FASE 1: PLANIFICACIÓN
│  → Objetivo claro · alcance exacto · preguntas resueltas · criterio de éxito
│
FASE 2: ANÁLISIS DE REQUISITOS
│  → Requisitos funcionales · No funcionales · Riesgos
│
FASE 3: DISEÑO DE ARQUITECTURA  ★ NUEVA
│  → ADRs · Contratos de interfaz · Estructura de módulos
│
FASE 4: CICLO DE MICRO-TAREAS (para cada tarea ≤ 50 líneas)
│  ┌────────────────────────────────────────────────────┐
│  │ 4.1 Verificar skills y contexto disponible         │
│  │ 4.2 Escribir tests PRIMERO (TDD estricto)          │
│  │ 4.3 Implementar código (≤ 50 líneas)               │
│  │ 4.4 Auto-revisión con checklist                    │
│  │ 4.5 Ejecutar tests — mostrar resultados REALES     │
│  │ 4.6 Si cobertura < 99% → refinar y repetir        │
│  └────────────────────────────────────────────────────┘
│
FASE 5: VALIDACIÓN INTEGRAL CON MÉTRICAS
│  → Seguridad · Tests · Calidad de código · Rendimiento · Arquitectura
│
FASE 6: GESTIÓN DE DEUDA TÉCNICA  ★ NUEVA
│  → Registrar · Priorizar · Planificar
│
FASE 7: REFINAMIENTO HASTA ≥ 99%
│  → Identificar → Corregir → Verificar → Confirmar
│
FASE 8: ENTREGA CON REPORTE COMPLETO
│  → Resumen · Tests · Decisiones · Checklist CI/CD · Próximos pasos
```

---

## 📋 Detalle de Fases

### Fase 1: Planificación

**Output:** Comprensión inequívoca de qué se va a construir.

Acciones:
- Analizar el objetivo general con precisión
- Identificar el alcance exacto (qué SÍ y qué NO está incluido)
- Hacer preguntas de clarificación antes de escribir código
- Identificar dependencias externas (APIs, librerías, servicios)
- Definir el criterio de éxito de la entrega

```
Preguntas a responder antes de continuar:
  ¿Qué debe hacer exactamente este código?
  ¿Quién lo usará y en qué contexto?
  ¿Qué está explícitamente FUERA del alcance?
  ¿Qué existe ya que se puede reutilizar?
  ¿Cuál es el criterio de aceptación?
```

---

### Fase 2: Análisis de Requisitos

**Output:** Lista completa de RF + RNF + riesgos identificados.

```
Requisitos Funcionales (RF):
  RF-01: Calcular IVA al 21% sobre precio base
  RF-02: Manejar precios con hasta 4 decimales
  RF-03: Retornar error si el precio es negativo

Requisitos No Funcionales (RNF):
  RNF-01: Tiempo de respuesta < 100ms para cálculos individuales
  RNF-02: Precisión decimal usando Decimal, no float
  RNF-03: Thread-safe para uso concurrente

Registro de Riesgos:
  RIESGO-01: Errores de redondeo con floats → Mitigación: usar Decimal
  RIESGO-02: Overflow con precios grandes → Mitigación: validar límites
```

---

### Fase 3: Diseño de Arquitectura ★ NUEVA

**Output:** ADRs + contratos de interfaz + estructura de módulos.

Documentar Architecture Decision Records (ADRs) **antes** de escribir implementaciones:

```markdown
## ADR-001: Librería de precisión decimal
- Contexto: Los cálculos financieros requieren precisión exacta
- Decisión: Usar decimal.Decimal nativo de Python
- Alternativas: float (rechazado — imprecisión), mpmath (sobredimensionado)
- Consecuencias: Código más verboso, pero correcto
```

Definir contratos de interfaz antes de implementar:

```python
def calculate_vat(
    base_price: Decimal,
    vat_rate: Decimal = Decimal("0.21"),
    currency: str = "EUR"
) -> VATResult:
    """
    Calcula el IVA sobre un precio base.

    Args:
        base_price: Precio sin IVA (debe ser > 0)
        vat_rate: Tasa de IVA como decimal (0.21 = 21%)
        currency: Código ISO de moneda

    Returns:
        VATResult con base, vat_amount y total

    Raises:
        ValueError: Si base_price <= 0
        ValueError: Si vat_rate no está en [0, 1]
    """
    ...
```

Estructura de módulos recomendada:
```
src/
├── domain/          # Lógica de negocio pura (sin dependencias externas)
│   ├── models.py
│   └── services.py
├── infrastructure/  # Adaptadores externos (DB, APIs, etc.)
└── interfaces/      # Controladores, CLI, endpoints de API

tests/
├── unit/            # Tests sin I/O
├── integration/     # Tests con infraestructura real
└── e2e/             # Tests de flujo completo
```

---

### Fase 4: Ciclo de Micro-Tareas

**Regla:** ≤ 50 líneas por micro-tarea. Una responsabilidad. Completamente testeable.

#### 4.2 — Escribir Tests PRIMERO (TDD Obligatorio)

```python
# tests/unit/test_vat_calculator.py
class TestCalculateVAT:

    # HAPPY PATH
    def test_standard_vat_calculation(self):
        result = calculate_vat(Decimal("100.00"))
        assert result.base == Decimal("100.00")
        assert result.vat_amount == Decimal("21.00")
        assert result.total == Decimal("121.00")

    # CASOS DE ERROR
    def test_negative_price_raises_error(self):
        with pytest.raises(ValueError, match="base_price must be positive"):
            calculate_vat(Decimal("-10.00"))

    def test_invalid_vat_rate_raises_error(self):
        with pytest.raises(ValueError, match="vat_rate must be between 0 and 1"):
            calculate_vat(Decimal("100.00"), vat_rate=Decimal("1.5"))

    # CASOS LÍMITE
    def test_minimum_valid_price(self):
        result = calculate_vat(Decimal("0.0001"))
        assert result.base == Decimal("0.0001")

    def test_zero_vat_rate(self):
        result = calculate_vat(Decimal("100.00"), vat_rate=Decimal("0"))
        assert result.vat_amount == Decimal("0")

    # SEGURIDAD
    def test_type_validation_rejects_float(self):
        with pytest.raises(TypeError):
            calculate_vat(10.0)  # float no aceptado

    # RENDIMIENTO
    def test_bulk_calculation_performance(self, benchmark):
        prices = [Decimal(str(i)) for i in range(1, 10001)]
        benchmark(lambda: [calculate_vat(p) for p in prices])
```

#### 4.3 — Implementar el Código (≤ 50 líneas)

```python
# src/domain/services.py
from decimal import Decimal
from dataclasses import dataclass

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
    if not isinstance(base_price, Decimal):
        raise TypeError("base_price must be Decimal, not float")
    if base_price <= Decimal("0"):
        raise ValueError("base_price must be positive")
    if not Decimal("0") <= vat_rate <= Decimal("1"):
        raise ValueError("vat_rate must be between 0 and 1")

    vat_amount = base_price * vat_rate
    return VATResult(
        base=base_price,
        vat_amount=vat_amount,
        total=base_price + vat_amount,
        currency=currency
    )
```

#### 4.4 — Checklist de Auto-Revisión

```
CALIDAD DE CÓDIGO:
  □ ¿Type hints completos en todas las funciones?
  □ ¿Docstring que explica el contrato?
  □ ¿Responsabilidad única por función?
  □ ¿Nombres semánticos (sin a, b, x)?
  □ ¿Sin duplicación de código innecesaria?

SEGURIDAD:
  □ ¿TODOS los inputs validados?
  □ ¿Outputs sanitizados antes de mostrar?
  □ ¿Sin credenciales hardcodeadas?
  □ ¿Tipos seguros usados (Decimal en lugar de float para dinero)?

MANTENIBILIDAD:
  □ ¿Puede otro dev entender esto en 2 minutos?
  □ ¿Nivel de abstracción consistente?
  □ ¿Errores registrados apropiadamente?
```

#### 4.5 — Ejecutar Tests y Mostrar Resultados

**OBLIGATORIO:** Mostrar siempre el output completo real.

```bash
$ pytest tests/unit/test_vat_calculator.py -v --cov=src --cov-report=term-missing

tests/unit/test_vat_calculator.py::TestCalculateVAT::test_standard_vat_calculation PASSED
tests/unit/test_vat_calculator.py::TestCalculateVAT::test_negative_price_raises_error PASSED
tests/unit/test_vat_calculator.py::TestCalculateVAT::test_invalid_vat_rate_raises_error PASSED
tests/unit/test_vat_calculator.py::TestCalculateVAT::test_minimum_valid_price PASSED
tests/unit/test_vat_calculator.py::TestCalculateVAT::test_zero_vat_rate PASSED
tests/unit/test_vat_calculator.py::TestCalculateVAT::test_type_validation_rejects_float PASSED
tests/unit/test_vat_calculator.py::TestCalculateVAT::test_bulk_calculation_performance PASSED

Name                    Stmts   Miss  Cover
-------------------------------------------
src/domain/services.py     14      0   100%
-------------------------------------------
TOTAL                       14      0   100%

7 passed in 0.43s
```

---

### Fase 5: Validación Integral con Métricas

| Dimensión | Checklist |
|-----------|-----------|
| **Seguridad** | Sin vulnerabilidades críticas (OWASP Top 10) · Validación de inputs · Sanitización de outputs · Sin secretos hardcodeados · Privilegio mínimo |
| **Tests** | 100% pasados · 0 fallidos · Cobertura ≥ 99% · Happy path + Error + Edge + Seguridad cubiertos |
| **Calidad de Código** | Type hints: 100% · Complejidad ciclomática < 10 · Sin duplicación · Nombres semánticos · SRP |
| **Rendimiento** | Sin queries N+1 · Índices en campos frecuentes · Paginación en listados · Timeouts configurados |
| **Arquitectura** | Sin importaciones circulares · Capas respetadas · Bajo acoplamiento · Interfaces bien definidas |

---

### Fase 6: Gestión de Deuda Técnica ★ NUEVA

No ignorar la deuda técnica — registrarla, priorizarla y planificarla.

```markdown
## DEUDA-001
- Tipo: Técnica (código)
- Descripción: calculate_vat no soporta conversión multi-moneda
- Impacto: Medio — funciona correctamente para moneda única
- Esfuerzo estimado: 2 horas
- Prioridad: Baja — no bloquea v1.0
- Plan: Implementar en v1.1 con servicio de tipos de cambio
```

Tipos a registrar:
- **Deuda técnica:** Código que funciona pero está por debajo del estándar
- **Deuda de tests:** Tests faltantes o insuficientes
- **Deuda de documentación:** Código sin explicar
- **Deuda de arquitectura:** Decisiones subóptimas que escalan mal

---

### Fase 7: Refinamiento hasta ≥ 99%

```
Si alguna métrica no alcanza el 99%:

1. IDENTIFICAR  — ¿Qué específicamente está por debajo del 99%?
2. CLASIFICAR   — Alta / Media / Baja prioridad
3. PLANIFICAR   — ¿Qué acción corregirá el problema?
4. EJECUTAR     — Implementar la corrección
5. VERIFICAR    — Re-ejecutar todos los tests
6. CONFIRMAR    — ¿≥ 99% ahora? Si no → volver al paso 1

⚠ Nunca avanzar a entrega sin confirmar ≥ 99%.
```

---

### Fase 8: Entrega con Reporte Completo

```markdown
# Reporte de Entrega — [Nombre de la Funcionalidad]
Fecha: YYYY-MM-DD
Implementado por: [Agente IA + revisor humano]
Versión: X.Y.Z

## Resumen de Implementación
[2-3 oraciones describiendo qué se implementó y cómo]

## Reporte de Tests
| Categoría       | Resultado  |
|-----------------|------------|
| Tests totales   | XX         |
| Pasados         | XX (100%)  |
| Fallidos        | 0          |
| Cobertura       | ≥ 99%      |
| Tiempo total    | X.XXs      |

## Output Completo de pytest
[Pegar aquí el output real de pytest]

## Decisiones Técnicas Clave
1. [Decisión]: [Justificación breve]
2. [Decisión]: [Justificación breve]

## Deuda Técnica Registrada
- DEUDA-001: [descripción] — Prioridad: Baja

## Checklist CI/CD
  □ Tests pasan en el pipeline
  □ Linting sin errores
  □ Type checking sin errores
  □ Security scan sin vulnerabilidades críticas

## Próximos Pasos Sugeridos
1. [Qué viene después en el backlog]
2. [Dependencias que esto desbloquea]
```

---

## 🔒 Reglas Absolutas (No Negociables)

```
REGLA 1 — Los tests son obligatorios
  ✗ "Los tests se agregarán después"
  ✓ Tests escritos ANTES del código de implementación

REGLA 2 — Mostrar resultados reales
  ✗ "Los tests deberían pasar"
  ✓ Output real de pytest con números exactos

REGLA 3 — Seguridad primero
  ✗ Hardcodear secretos "por ahora"
  ✓ Variables de entorno / vault desde el primer commit

REGLA 4 — Cobertura ≥ 99% o no hay entrega
  ✗ Entregar con 85% y "casi completo"
  ✓ Iterar hasta ≥ 99% antes de marcar como entregado

REGLA 5 — Documentar decisiones
  ✗ "El código se explica solo"
  ✓ ADRs para decisiones no triviales, docstrings para todo lo público

REGLA 6 — Registrar deuda  ★ NUEVA
  ✗ Ignorar problemas conocidos "para después"
  ✓ Registrar en formato DEUDA-XXX con prioridad y plan
```

---

## 🤖 Soporte Multi-Agente ★ NUEVO

El Método PDCA-T v3.0 incluye adapters para cada agente de IA principal:

| Agente | Adapter | Notas |
|--------|---------|-------|
| **Cursor** | `adapters/cursor.md` | Regla con `trigger: always_on` |
| **Windsurf** | `adapters/windsurf.md` | Se añade al final de `.windsurfrules` |
| **GitHub Copilot** | `adapters/copilot.md` | En `.github/copilot-instructions.md` |
| **Claude Code** | `adapters/claudecode.md` | En `CLAUDE.md` |
| **Claude.ai** | `adapters/claudeai.md` | Pegar en system prompt o conversación |
| **ChatGPT / GPT-4o** | `adapters/openai.md` | Pegar en instrucciones personalizadas |
| **Google Antigravity** | `adapters/antigravity.md` | `.agent/rules/method-pdca-t.md` |
| **Google Antigravity** | `adapters/antigravity.md` | `.agent/rules/method-pdca-t.md` |
| **Aider** | `adapters/aider.md` | `--system-prompt` o `.aider.conf.yml` |
| **Cualquier otro agente** | `adapters/generic.md` | Pegar en el contexto del agente |

Cada adapter está ajustado a cómo ese agente específico lee y aplica instrucciones — mismo método, optimizado por agente.

---

## 🛠️ Configuración CI/CD Recomendada ★ NUEVA

```yaml
# .github/workflows/quality.yml
name: PDCA-T Quality Gate

on: [push, pull_request]

jobs:
  quality:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Configurar Python
        uses: actions/setup-python@v5
        with:
          python-version: "3.11"

      - name: Instalar dependencias
        run: pip install -r requirements.txt

      - name: Lint (ruff)
        run: ruff check src/ tests/

      - name: Type checking (mypy)
        run: mypy src/

      - name: Escaneo de seguridad (bandit)
        run: bandit -r src/ -ll

      - name: Tests con umbral de cobertura
        run: |
          pytest tests/ \
            --cov=src \
            --cov-fail-under=99 \
            --cov-report=xml \
            -v

      - name: Subir cobertura
        uses: codecov/codecov-action@v4
```

---

## 📁 Estructura del Repositorio

```
method_pdca-t/
├── METHOD.md                        ← Documentación completa del método
├── README.md                        ← Versión en inglés
├── README_ES.md                     ← Este archivo (Español)
│
├── adapters/
│   ├── cursor.md                    ← Cursor
│   ├── windsurf.md                  ← Windsurf
│   ├── copilot.md                   ← GitHub Copilot
│   ├── claudecode.md                ← Claude Code
│   ├── claudeai.md                  ← Claude.ai
│   ├── openai.md                    ← ChatGPT / GPT-4o
│   ├── aider.md                     ← Aider
│   └── generic.md                   ← Cualquier otro agente
│
├── .cursor/
│   ├── rules/
│   │   └── METHOD-PDCA-T.md         ← Regla de activación automática en Cursor
│   └── skills/
│       └── method-pdca-t/
│           └── SKILL.md
│
├── templates/
│   ├── delivery-report.md           ← Plantilla de reporte de entrega
│   ├── adr-template.md              ← Architecture Decision Record
│   └── debt-register.md             ← Registro de deuda técnica
│
├── examples/
│   ├── tax-calculator/              ← Ejemplo completo trabajado
│   └── rest-api/                    ← Ejemplo de API REST
│
├── docs/
│   ├── INSTALLATION.md
│   └── USAGE.md
│
├── .github/
│   └── workflows/
│       └── quality.yml              ← Pipeline CI/CD
│
├── CHANGELOG.md
├── CONTRIBUTING.md
└── LICENSE
```

---

## 📊 Objetivos de Calidad de un Vistazo

| Métrica | Objetivo |
|---------|----------|
| Cobertura de tests | ≥ 99% |
| Tests fallidos | 0 |
| Líneas por micro-tarea | ≤ 50 |
| Complejidad ciclomática | < 10 por función |
| Secretos hardcodeados | 0 |
| Cobertura de type hints (público) | 100% |

---

## 🆚 Qué Cambió en v3.0

| Aspecto | v1.0 Original | v3.0 Mejorado |
|---------|--------------|---------------|
| Fases | 6 | 8 |
| Fase de diseño de arquitectura | ❌ | ✅ Fase 3 con ADRs |
| TDD explícito | Parcial | ✅ Tests ANTES del código |
| Gestión de deuda técnica | ❌ | ✅ Fase 6 con formato DEUDA-XXX |
| Pipeline CI/CD | ❌ | ✅ GitHub Actions incluido |
| Architecture Decision Records | ❌ | ✅ Template incluido |
| Tipos de tests | Unit básicos | ✅ Unit + Integration + E2E |
| Adapters multi-agente | Solo Cursor | ✅ 8 agentes soportados |
| Reporte de entrega | Básico | ✅ Completo con checklist CI/CD |
| Templates de deuda técnica | ❌ | ✅ Template completo incluido |
| Instalación CLI con enet | ❌ | ✅ `enet install pdca-t` |

---

## 📖 Métodos Relacionados

El Método PDCA-T funciona mejor junto a:

- **[Method Modular Design](https://github.com/exchanet/method_modular_design)** ⭐ Recomendado — Arquitectura modular limpia con Admin Panel auto-generado. *Modular Design construye el sistema correcto. PDCA-T lo construye bien.*
- **[Method IRIS](https://github.com/exchanet/method_IRIS)** — Mejora continua de sistemas existentes.
- **[Method Enterprise Builder](https://github.com/exchanet/method_enterprise_builder_planning)** — Planificación a gran escala para proyectos complejos.

---

## 🌐 Leer en Inglés

**📖 [Read in English](./README.md)**

---

## 🤝 Contribuir

Las contribuciones son bienvenidas. Los ejemplos de nuevos adapters, templates específicos de stack y demos de proyectos reales son especialmente apreciados.

1. Haz fork del repositorio
2. Crea una rama de feature (`git checkout -b feature/mejora`)
3. Haz commit de tus cambios
4. Haz push y abre un Pull Request

---

## 📄 Licencia

MIT — Libre para usar, modificar y distribuir con atribución.

---

## 👤 Autor

**Francisco J. Bernades**

- GitHub: [@exchanet](https://github.com/exchanet)
- Repositorio: [github.com/exchanet/method_pdca-t_coding](https://github.com/exchanet/method_pdca-t_coding)

---

*"Codificar con IA no es diferente a codificar en equipo — la disciplina del proceso es lo que separa el prototipo del software de producción."*
