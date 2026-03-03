# Usage Guide / Guia de Uso

## ENGLISH

### Starting a task with PDCA-T

- Cursor / Windsurf / Copilot / Claude Code: Method activates automatically. Just start working.
- Claude.ai / ChatGPT: Paste adapter content at the start of conversation.

### Example prompts

New feature:
  "Implement a user auth module with JWT + refresh tokens. Stack: FastAPI + PostgreSQL. Apply Method PDCA-T."

Bug fix:
  "Fix the VAT calculator bug when price has more than 4 decimals. Apply Method PDCA-T with full test coverage."

Refactor:
  "Refactor the payment module to Clean Architecture. Use Method PDCA-T. Document all decisions with ADRs."

### What to expect

The agent will:
1. Ask clarifying questions until objective is unambiguous
2. List FR + NFR requirements and risks
3. Write ADRs before any code
4. Write tests FIRST (≤ 50 lines per micro-task)
5. Show real pytest output after every task
6. Iterate until coverage is ≥ 99%
7. Register DEBT-XXX for any known issues
8. Close with a full delivery report

### Reading the delivery report

- Test table: Confirms 100% pass + ≥ 99% coverage
- Full pytest output: Verify numbers are real not estimated
- Key decisions: ADR references explain trade-offs
- DEBT-XXX list: What was deferred and the plan
- CI/CD checklist: All gates green before merging

### Combining with Method Modular Design

  enet install modular-design
  enet install pdca-t

Modular Design defines module manifests. PDCA-T ensures each module is built with quality.

---

## ESPANOL

### Comenzar una tarea con PDCA-T

- Cursor / Windsurf / Copilot / Claude Code: El metodo se activa automaticamente.
- Claude.ai / ChatGPT: Pegar el adapter al inicio de la conversacion.

### Prompts de ejemplo

Nueva funcionalidad:
  "Implementa un modulo de autenticacion con JWT. Stack: FastAPI + PostgreSQL. Aplica el Metodo PDCA-T."

Bug fix:
  "Hay un bug en la calculadora de IVA con precios de mas de 4 decimales. Corrjelo con PDCA-T."

### Que esperar del agente

1. Hara preguntas hasta que el objetivo sea inequivoco
2. Listara RF + RNF e identificara riesgos
3. Escribira ADRs antes de cualquier codigo
4. Escribira tests PRIMERO (cada micro-tarea le 50 lineas)
5. Mostrara el output real de pytest tras cada tarea
6. Iterara hasta cobertura >= 99%
7. Registrara DEUDA-XXX para problemas conocidos
8. Cerrara con reporte completo de entrega

### Solucion de problemas

El agente no aplica PDCA-T:
  - Cursor: verificar .cursor/rules/method-pdca-t.md con trigger: always_on
  - Claude Code: verificar CLAUDE.md en raiz del proyecto
  - Otros: volver a pegar el adapter al inicio de la conversacion

Cobertura por debajo del 99%:
  - Pedir al agente la columna Missing de pytest
  - Pedirle que explique las lineas sin cubrir y agregue tests
