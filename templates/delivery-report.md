# Delivery Report Template / Plantilla de Reporte de Entrega

---

## 🇬🇧 ENGLISH

```markdown
# Delivery Report — [Feature Name]

**Date:** YYYY-MM-DD
**Implemented by:** [AI Agent] + [Human Reviewer]
**Version:** X.Y.Z
**Branch:** feature/[name]
**Related task/issue:** #XXX

---

## Implementation Summary
[2-3 sentences describing what was implemented, the approach chosen,
and any significant constraint that shaped the solution.]

---

## Test Report

| Category         | Result     |
|------------------|------------|
| Total tests      | XX         |
| Passed           | XX (100%)  |
| Failed           | 0          |
| Skipped          | 0          |
| Coverage         | ≥ 99%      |
| Total time       | X.XXs      |

### Coverage by module

| Module                  | Stmts | Miss | Cover | Missing |
|-------------------------|-------|------|-------|---------|
| src/domain/models.py    | XX    | 0    | 100%  |         |
| src/domain/services.py  | XX    | 0    | 100%  |         |
| src/infrastructure/...  | XX    | 0    | 100%  |         |
| **TOTAL**               | XX    | 0    | ≥99%  |         |

---

## Full Test Output (unedited)

[Paste the exact, unedited pytest output here. Never summarize.]

```
$ pytest tests/ -v --cov=src --cov-report=term-missing --tb=short
...
```

---

## Key Technical Decisions

1. **[Decision title]**
   - Choice: [What was decided]
   - Justification: [Why — reference ADR-XXX if applicable]
   - Alternatives considered: [What else was evaluated]

2. **[Decision title]**
   - Choice: [What was decided]
   - Justification: [Why]

---

## Technical Debt Registered

| ID       | Type          | Description          | Impact | Priority | Plan    |
|----------|---------------|----------------------|--------|----------|---------|
| DEBT-001 | [type]        | [description]        | Medium | Low      | v1.1    |

*None registered in this delivery.* (delete if debt exists)

---

## CI/CD Checklist

- [ ] All tests pass in CI pipeline
- [ ] Linting passes without errors (ruff / eslint)
- [ ] Type checking passes (mypy --strict / tsc)
- [ ] Security scan passes (bandit / npm audit)
- [ ] Coverage ≥ 99% confirmed by pipeline gate
- [ ] No secrets detected in codebase (gitleaks / trufflehog)
- [ ] Dependency vulnerabilities checked (pip-audit / npm audit)

---

## Suggested Next Steps

1. [Immediate next item in the backlog]
2. [What this delivery unblocks]
3. [Planned follow-up for any registered debt]
```

---

## 🇪🇸 ESPAÑOL

```markdown
# Reporte de Entrega — [Nombre de la Funcionalidad]

**Fecha:** YYYY-MM-DD
**Implementado por:** [Agente IA] + [Revisor humano]
**Versión:** X.Y.Z
**Rama:** feature/[nombre]
**Tarea/issue relacionado:** #XXX

---

## Resumen de Implementación
[2-3 oraciones describiendo qué se implementó, el enfoque elegido
y cualquier restricción significativa que haya dado forma a la solución.]

---

## Reporte de Tests

| Categoría        | Resultado  |
|------------------|------------|
| Tests totales    | XX         |
| Pasados          | XX (100%)  |
| Fallidos         | 0          |
| Omitidos         | 0          |
| Cobertura        | ≥ 99%      |
| Tiempo total     | X.XXs      |

### Cobertura por módulo

| Módulo                  | Stmts | Miss | Cover | Faltantes |
|-------------------------|-------|------|-------|-----------|
| src/domain/models.py    | XX    | 0    | 100%  |           |
| src/domain/services.py  | XX    | 0    | 100%  |           |
| src/infrastructure/...  | XX    | 0    | 100%  |           |
| **TOTAL**               | XX    | 0    | ≥99%  |           |

---

## Output Completo de Tests (sin editar)

[Pegar aquí el output exacto y sin editar de pytest. Nunca resumir.]

```
$ pytest tests/ -v --cov=src --cov-report=term-missing --tb=short
...
```

---

## Decisiones Técnicas Clave

1. **[Título de la decisión]**
   - Elección: [Qué se decidió]
   - Justificación: [Por qué — referenciar ADR-XXX si aplica]
   - Alternativas consideradas: [Qué más se evaluó]

2. **[Título de la decisión]**
   - Elección: [Qué se decidió]
   - Justificación: [Por qué]

---

## Deuda Técnica Registrada

| ID        | Tipo          | Descripción          | Impacto | Prioridad | Plan    |
|-----------|---------------|----------------------|---------|-----------|---------|
| DEUDA-001 | [tipo]        | [descripción]        | Medio   | Baja      | v1.1    |

*Ninguna registrada en esta entrega.* (eliminar si existe deuda)

---

## Checklist CI/CD

- [ ] Todos los tests pasan en el pipeline CI
- [ ] Linting pasa sin errores (ruff / eslint)
- [ ] Type checking pasa (mypy --strict / tsc)
- [ ] Security scan pasa (bandit / npm audit)
- [ ] Cobertura ≥ 99% confirmada por el umbral del pipeline
- [ ] Sin secretos detectados en el codebase (gitleaks / trufflehog)
- [ ] Vulnerabilidades en dependencias verificadas (pip-audit / npm audit)

---

## Próximos Pasos Sugeridos

1. [Siguiente elemento inmediato en el backlog]
2. [Qué desbloquea esta entrega]
3. [Seguimiento planificado para la deuda registrada]
```
