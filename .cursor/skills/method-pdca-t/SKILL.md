---
name: method-pdca-t
description: Apply the PDCA-T quality methodology to a coding task. Use when starting any new feature, function, module, or fix that requires systematic quality assurance with ≥99% test coverage, TDD, architecture design, and a documented delivery report.
---

# Skill: Method PDCA-T

You have been invoked to apply the PDCA-T quality methodology to this task.

## How to use this skill

When a user asks you to implement something using PDCA-T (or this skill is referenced), execute the full 8-phase cycle:

1. **Ask** for any missing information before starting (Phase 1)
2. **Document** requirements and risks (Phase 2)
3. **Design** architecture with ADRs and interface contracts (Phase 3)
4. **Implement** via micro-tasks with TDD (Phase 4) — show real test output
5. **Validate** across all 5 dimensions (Phase 5)
6. **Register** technical debt (Phase 6)
7. **Refine** until ≥ 99% (Phase 7)
8. **Deliver** with full report (Phase 8)

## Quick reference — Phase 4 sub-cycle

For each micro-task (≤ 50 lines):
```
→ Write tests FIRST (happy path + error + edge + security)
→ Implement (type hints + docstrings + SRP + no hardcoding)
→ Self-review checklist
→ Run pytest — show complete real output
→ If coverage < 99%: identify gap → add tests → re-run
```

## Non-negotiable rules
- Tests before code — always
- Real test output — always
- No hardcoded secrets — always
- Coverage ≥ 99% before delivery
- All known issues as DEBT-XXX

## When to use this skill
- Starting a new feature or module
- Implementing a bug fix that needs regression coverage
- Refactoring existing code to meet quality standards
- Any task where the user asks for "PDCA-T quality" or "full coverage"

## Related skills
- Check .cursor/skills/ for stack-specific skills (frontend-design, etc.)
- This skill pairs with Method Modular Design for architectural tasks
