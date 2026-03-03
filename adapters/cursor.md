---
description: Method PDCA-T — Systematic quality cycle for AI-assisted coding
trigger: always_on
---

# METHOD PDCA-T — Active for all tasks

You are operating under the PDCA-T quality methodology. Apply this cycle to every coding task.

## THE 8-PHASE MANDATORY CYCLE

### PHASE 1 — PLANNING
Before writing any code:
- State the exact objective in one sentence
- Define what IS and IS NOT in scope
- Ask clarifying questions if anything is ambiguous
- Identify external dependencies
- Define the acceptance criterion

### PHASE 2 — REQUIREMENTS ANALYSIS
- List Functional Requirements (FR-01, FR-02…)
- List Non-Functional Requirements (NFR-01, NFR-02…)
- Identify risks with mitigation strategy

### PHASE 3 — ARCHITECTURE DESIGN
Before any implementation:
- Write ADRs for non-trivial decisions (context / decision / alternatives / consequences)
- Define interface contracts (signatures + docstrings) before implementing
- Define module structure (domain / infrastructure / interfaces)

### PHASE 4 — MICRO-TASK CYCLE (repeat for each task ≤ 50 lines)

**4.1** Check available skills in `.cursor/skills/`
**4.2** Write tests FIRST — never write implementation before tests:
  - Happy path · Error cases · Edge cases · Security · Performance (if applicable)
**4.3** Implement code:
  - Complete type hints · Docstrings · Single responsibility · Zero hardcoding · Specific exception handling
**4.4** Self-review checklist:
  - Type hints complete? · Security vulnerabilities? · Code duplication? · Semantic names? · Single responsibility?
**4.5** Execute tests and show REAL output (exact pytest output with numbers)
**4.6** If coverage < 99% → identify gap → add tests or fix code → repeat from 4.5

### PHASE 5 — INTEGRAL VALIDATION
After all micro-tasks:
- Security: no OWASP Top 10 issues · inputs validated · outputs sanitized · no hardcoded secrets
- Tests: 100% passed · 0 failed · coverage ≥ 99%
- Code quality: type hints 100% · cyclomatic complexity < 10 · no duplication · SRP
- Performance: no N+1 · indexes · pagination · timeouts
- Architecture: no circular imports · layers respected · low coupling

### PHASE 6 — TECHNICAL DEBT MANAGEMENT
Register any known issues in DEBT-XXX format:
```
DEBT-001: [description] | Impact: High/Medium/Low | Effort: Xh | Priority: High/Medium/Low | Plan: [action]
```

### PHASE 7 — REFINEMENT TO ≥ 99%
If any metric is below target:
Identify → Classify → Plan → Execute → Verify → Confirm ≥ 99%
Never deliver without confirming ≥ 99%.

### PHASE 8 — DELIVERY REPORT
Always close with:
- Implementation summary (2-3 sentences)
- Test report table: total / passed / failed / coverage / time
- Full pytest output
- Key technical decisions with justifications
- Technical debt registered
- CI/CD checklist
- Suggested next steps

## ABSOLUTE RULES
1. Tests BEFORE implementation — never the reverse
2. Show REAL test results — never say "tests should pass"
3. No hardcoded secrets — environment variables from commit 1
4. Coverage ≥ 99% before any delivery
5. Document non-trivial decisions with ADRs
6. Register all known issues as DEBT-XXX

## TEST CATEGORIES (all required)
- Happy path (normal operation)
- Error cases (validation, exceptions)
- Edge cases (boundaries, empty, zero, max)
- Security (injection, type coercion, permissions)
- Performance (if latency-sensitive)

## CODE STANDARDS
- Python 3.11+ type hints or TypeScript strict mode
- Decimal (not float) for monetary calculations
- Specific exceptions (not bare `except:`)
- Structured logging with context
- Zero hardcoded configuration values
