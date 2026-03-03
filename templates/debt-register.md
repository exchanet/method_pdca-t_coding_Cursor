# Technical Debt Register / Registro de Deuda Tecnica

---

## ENGLISH

### Summary Table

| ID | Type | Description | Impact | Effort | Priority | Status | Target | Added |
|----|------|-------------|--------|--------|----------|--------|--------|-------|
| DEBT-001 | [type] | [description] | Medium | 2h | Low | Open | v1.1 | YYYY-MM-DD |

### Debt Types
- Technical: Code that works but is below standard quality
- Test: Missing or insufficient test coverage
- Documentation: Unexplained or missing documentation
- Architecture: Suboptimal design that scales poorly
- Security: Known risk not yet mitigated
- Performance: Known bottleneck not yet optimized

### Priority Guide
- High: Resolve in next sprint. Blocks quality or security.
- Medium: Resolve in 2-3 sprints. Impacts maintainability.
- Low: Tracked. Planned for future version. No immediate impact.

### DEBT-XXX Detail Template

DEBT-XXX: [Short title]
- Type: Technical | Test | Documentation | Architecture | Security | Performance
- Description: [What the problem is and why it exists]
- Impact: High | Medium | Low -- [one-line justification]
- Estimated effort: Xh
- Priority: High | Medium | Low
- Status: Open | In Progress | Resolved
- Plan: [Specific action and target version/sprint]
- Added: YYYY-MM-DD
- Resolved: YYYY-MM-DD (fill when resolved)
- Related: ADR-XXX | FR-NN | NFR-NN

### Example

DEBT-001: Multi-currency support missing in VAT calculator
- Type: Technical
- Description: calculate_vat() only supports EUR. Deferred from v1.0 scope.
- Impact: Medium -- works for single-currency. Blocks international expansion.
- Estimated effort: 4h
- Priority: Low -- not blocking for current customer base
- Status: Open
- Plan: Implement in v1.1 using ECB exchange rate API with daily cache
- Added: 2024-03-15
- Related: FR-08 (future), ADR-002

---

## ESPANOL

### Tabla Resumen

| ID | Tipo | Descripcion | Impacto | Esfuerzo | Prioridad | Estado | Objetivo | Anadida |
|----|------|-------------|---------|----------|-----------|--------|----------|---------|
| DEUDA-001 | [tipo] | [descripcion] | Medio | 2h | Baja | Abierta | v1.1 | YYYY-MM-DD |

### Tipos de Deuda
- Tecnica: Codigo que funciona pero por debajo del estandar
- Tests: Cobertura faltante o insuficiente
- Documentacion: Documentacion inexplicada o faltante
- Arquitectura: Diseno suboptimo que escala mal
- Seguridad: Riesgo conocido no mitigado
- Rendimiento: Cuello de botella conocido no optimizado

### Guia de Prioridades
- Alta: Resolver en el proximo sprint. Bloquea calidad o seguridad.
- Media: Resolver en 2-3 sprints. Impacta mantenibilidad.
- Baja: Registrada. Planificada para version futura. Sin impacto inmediato.

### Template DEUDA-XXX

DEUDA-XXX: [Titulo corto]
- Tipo: Tecnica | Tests | Documentacion | Arquitectura | Seguridad | Rendimiento
- Descripcion: [Cual es el problema y por que existe]
- Impacto: Alto | Medio | Bajo -- [justificacion en una linea]
- Esfuerzo estimado: Xh
- Prioridad: Alta | Media | Baja
- Estado: Abierta | En Progreso | Resuelta
- Plan: [Accion especifica y version/sprint objetivo]
- Anadida: YYYY-MM-DD
- Resuelta: YYYY-MM-DD (completar cuando se resuelva)
- Relacionada: ADR-XXX | RF-NN | RNF-NN
