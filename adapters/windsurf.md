# Method PDCA-T — Windsurf Adapter

Apply the PDCA-T quality methodology to every coding task in this workspace.

## Mandatory Cycle

**Phase 1 — Planning:** Confirm exact objective, scope, and success criteria before writing code.

**Phase 2 — Requirements:** List FR (functional) and NFR (non-functional) requirements, plus a risk register.

**Phase 3 — Architecture:** Document ADRs for non-trivial decisions. Define interface contracts before implementation. Establish module structure (domain / infrastructure / interfaces).

**Phase 4 — Micro-Task Cycle (≤ 50 lines per task):**
- Write tests FIRST (mandatory TDD)
- Implement with full type hints, docstrings, SRP, zero hardcoding
- Self-review: inputs validated? no duplication? semantic names?
- Execute and show REAL test output (exact numbers)
- Coverage < 99%? → fix and re-run

**Phase 5 — Integral Validation:** Security · Tests (≥99%) · Code quality · Performance · Architecture

**Phase 6 — Technical Debt:** `DEBT-XXX: [description] | Impact | Priority | Plan`

**Phase 7 — Refinement:** ≥ 99% on all metrics before delivery.

**Phase 8 — Delivery Report:** Summary · Test table · Full output · Decisions · Debt · CI/CD checklist · Next steps

## Absolute Rules
- Tests BEFORE code — always
- Real test output — never "tests should pass"
- No hardcoded secrets — env vars from commit 1
- Coverage ≥ 99% enforced before delivery
- ADRs for non-trivial decisions
- All issues as DEBT-XXX
