# Method PDCA-T — Active in this project

This project uses the **PDCA-T quality methodology**. Apply this cycle to every coding task without exception.

## When to apply
Every time you write, edit, or review code in this repository.

## The 8-Phase Cycle

### Phase 1 — Planning
State the exact objective, scope, and acceptance criteria before writing code. Ask questions if ambiguous.

### Phase 2 — Requirements Analysis
List FR (functional), NFR (non-functional), and risks with mitigations.

### Phase 3 — Architecture Design
Write ADRs and define interface contracts (signatures + docstrings) before any implementation. Define module structure.

### Phase 4 — Micro-Task Cycle (≤ 50 lines per task)
```
4.1 → Check available context and reusable code
4.2 → Write tests FIRST (mandatory TDD)
4.3 → Implement code (≤ 50 lines, full type hints, docstrings, SRP)
4.4 → Self-review: type hints? security? duplication? semantic names?
4.5 → Execute tests — show REAL output with exact numbers
4.6 → Coverage < 99%? → Identify gap → Fix → Repeat from 4.5
```

### Phase 5 — Integral Validation
Security · Tests (≥99%) · Code quality · Performance · Architecture

### Phase 6 — Technical Debt
Register issues as: `DEBT-XXX: [description] | Impact | Effort | Priority | Plan`

### Phase 7 — Refinement
Iterate until ≥ 99% on all metrics. Never deliver below threshold.

### Phase 8 — Delivery Report
Summary · Test table · Full pytest output · Key decisions · Debt registered · CI/CD checklist · Next steps

## Non-Negotiable Rules
- Tests BEFORE code — always
- Show REAL pytest output — never summarize as "tests pass"
- No hardcoded secrets — env vars from day 1
- Coverage ≥ 99% — enforced before delivery
- ADRs for non-trivial decisions
- All known issues registered as DEBT-XXX

## Test Requirements (all tasks)
Every function must have: happy path · error cases · edge cases · security test · performance test (if applicable)

## Code Standards
- Full type hints (Python 3.11+ or TypeScript strict)
- `decimal.Decimal` for monetary values — never `float`
- Specific exceptions — never bare `except:`
- Structured logging with context fields
- Zero hardcoded configuration
