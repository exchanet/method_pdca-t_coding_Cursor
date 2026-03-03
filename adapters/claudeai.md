# Method PDCA-T — Quality Framework for this session

Apply the PDCA-T methodology to every coding task in this conversation.

## Mandatory Cycle

**Phase 1 — Planning:** Confirm exact objective, scope, and acceptance criteria before writing any code.

**Phase 2 — Requirements:** List functional (FR) and non-functional (NFR) requirements, plus risks with mitigations.

**Phase 3 — Architecture:** Write ADRs for non-trivial decisions. Define interface contracts (function signatures + docstrings) before implementing.

**Phase 4 — Micro-Tasks (≤ 50 lines each):**
1. Write tests FIRST — always before implementation
2. Implement code (type hints, docstrings, single responsibility, no hardcoding)
3. Self-review: type hints complete? inputs validated? no duplication? semantic names?
4. Show REAL test output with exact numbers (pytest or equivalent)
5. If coverage < 99% → fix and show updated results

**Phase 5 — Validation:** Confirm security (OWASP Top 10), tests (≥99% coverage), code quality (complexity < 10), performance (no N+1), architecture (no circular imports).

**Phase 6 — Technical Debt:** Register any known issues as `DEBT-XXX: [description] | Impact | Priority | Plan`

**Phase 7 — Refinement:** Do not advance to delivery until all metrics reach ≥ 99%.

**Phase 8 — Delivery Report:** Always close with: summary + test table + full test output + key decisions + debt registered + next steps.

## Rules (never break these)
- Tests written BEFORE implementation code
- Show actual test output — never say "it should work"
- No hardcoded secrets — environment variables always
- Coverage ≥ 99% before marking anything as done
- Register all known issues as DEBT-XXX

## Required Test Coverage
Happy path · Error cases · Edge cases (boundaries, empty, null) · Security · Performance (if relevant)
