# Método PDCA-T: una regla, una skill, especificación bilingüe

El método PDCA-T es **uno solo**, en **8 fases**. En el repositorio hay una única regla y una única skill (en inglés). La especificación técnica canónica es bilingüe.

## Referencia canónica

- **METHOD.md** — Especificación técnica completa con secciones en **inglés y español**. Define las 8 fases, ADRs, contratos de interfaz, DEBT-XXX/DEUDA-XXX y criterios de calidad. Quienes trabajen en español pueden usar la sección ES como referencia; la regla activa en Cursor sigue siendo METHOD-PDCA-T.md.

## Artefactos en el repositorio

| Artefacto | Ubicación |
|-----------|-----------|
| Regla (rule) | `.cursor/rules/METHOD-PDCA-T.md` (inglés) |
| Skill | `.cursor/skills/method-pdca-t/SKILL.md` (inglés) |

No existe regla ni skill en español en el repo; la única fuente de verdad operativa es la regla en inglés. METHOD.md proporciona la misma especificación en ambos idiomas.

## Las 8 fases

1. **Planning / Planificación** — Objetivo, alcance, criterios de aceptación.
2. **Requirements analysis / Análisis de requisitos** — FR/RF, NFR/RNF, registro de riesgos.
3. **Architecture design / Diseño de arquitectura** — ADRs, contratos de interfaz, estructura de módulos.
4. **Micro-task cycle / Ciclo de micro-tareas** — ≤ 50 líneas, tests primero, pytest con output real, cobertura ≥ 99%.
5. **Integral validation / Validación integral** — Seguridad, tests, calidad, rendimiento, arquitectura.
6. **Technical debt / Gestión de deuda técnica** — DEBT-XXX (en METHOD.md sección ES: DEUDA-XXX), con tipo, impacto, plan.
7. **Refinement / Refinamiento** — Hasta ≥ 99% en todas las dimensiones.
8. **Delivery / Entrega** — Reporte completo con evidencia de tests y deuda registrada.

## Mantenimiento

Al actualizar el método:

1. Actualizar **METHOD.md** (secciones EN y ES si aplica).
2. Mantener **method-pdca-t** (skill) y **METHOD-PDCA-T.md** (regla) alineados con METHOD.md.
