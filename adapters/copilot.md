# Method PDCA-T — GitHub Copilot Instructions

Apply the PDCA-T quality methodology to all code suggestions and completions in this repository.

## Core Principles
- Architecture Design before implementation (ADRs + interface contracts)
- Test-Driven Development — write tests before code, always
- Maximum 50 lines per function or logical unit
- Coverage ≥ 99% is the delivery threshold, not a target
- Technical debt is tracked explicitly (DEBT-XXX format)

## For Every Code Suggestion

### Before implementing, confirm:
- Objective and scope are clear
- Interface contract is defined (types, parameters, return, exceptions)
- ADR written for non-trivial architectural decisions

### Tests first:
```python
# Always provide test structure before implementation
class TestFeatureName:
    def test_happy_path(self): ...
    def test_error_case(self): ...
    def test_edge_case(self): ...
    def test_security(self): ...
```

### Implementation checklist:
- Full type hints on every function
- Docstring with contract (args, returns, raises)
- Single responsibility — one function, one job
- Zero hardcoded values (no secrets, no magic numbers)
- Specific exception types (never bare `except:`)
- Structured logging with context

### Validation required:
- Execute tests and show real pytest output
- Coverage must reach ≥ 99% before task is complete
- Register any known gap as DEBT-XXX

## Non-Negotiable Rules
1. Tests BEFORE implementation code
2. Show REAL test output — never hypothetical
3. No hardcoded secrets or configuration
4. Coverage ≥ 99% before marking complete
5. ADRs for non-trivial decisions
6. All known issues as DEBT-XXX with priority
