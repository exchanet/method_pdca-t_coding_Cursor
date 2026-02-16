---
trigger: always_on
---

# PDCA-T ENHANCED WORKING METHOD WITH ≥99% VALIDATION

This method must be applied ALWAYS, for ALL tasks, without exception. It is the default way of working for the agent.

## THE METHOD (PDCA-T Enhanced Cycle with ≥99% Validation)

Whenever you receive a task, you must execute this cycle:

```
PHASE 1: PLANNING
│
▼
PHASE 2: REQUIREMENTS ANALYSIS
│
▼
PHASE 3: MICRO-TASK DIVISION
│
▼
┌─────────────────────────────────────────────────┐
│  FOR EACH MICRO-TASK:                           │
│  ┌─────────────────────────────────────────┐    │
│  │ 3.1 Check available skills              │    │
│  │ 3.2 Execute with applied skill           │    │
│  │ 3.3 Self-review                           │    │
│  │ 3.4 Generate COMPLETE tests               │    │
│  │ 3.5 EXECUTE tests and show results       │    │
│  │ 3.6 If coverage < 99% → review and improve│    │
│  └─────────────────────────────────────────┘    │
└─────────────────────────────────────────────────┘
│
▼
PHASE 4: INTEGRAL VALIDATION WITH METRICS
│
▼
PHASE 5: REFINEMENT UNTIL ≥99%
│
▼
PHASE 6: DELIVERY WITH TEST REPORT
```

## PHASE 1: INITIAL PLANNING

- Analyze the general objective
- Identify the exact scope
- Ask me if something is unclear
- **Output:** Clear understanding of what needs to be done

## PHASE 2: REQUIREMENTS ANALYSIS

- Identify functional requirements
- Identify non-functional requirements (security, performance, scalability)
- Identify potential risks
- **Output:** List of requirements and risks

## PHASE 3: MICRO-TASK DIVISION

Divide the work into tasks of **MAXIMUM 50 LINES OF CODE** each:
- Task 1: [description]
- Task 2: [description]
- etc.

For **EACH micro-task**, execute this sub-cycle:

### 3.1 Check Available Skills

Before writing code, ask yourself:
- Is there a skill in my repository that I can use for this task?
- If YES: apply it automatically
- If NO: execute the task with general best practices

### 3.2 Execute the Task

Write code following:
- Complete type hints (Python 3.12+) or complete TypeScript types
- Security best practices
- Zero hardcoding (everything configurable)
- Specific exception handling
- Structured logging

### 3.3 Immediate Self-Review

Review the code you just wrote:
- Does it have type hints?
- Are there security vulnerabilities?
- Is there code duplication?
- Is it readable and maintainable?
- Does it follow language best practices?

### 3.4 Generate COMPLETE Tests

Write unit tests for this task covering:

**MINIMUM REQUIRED:**
- [ ] Happy path test
- [ ] Error case test (validation, exceptions)
- [ ] Edge case test
- [ ] Boundary value test
- [ ] Invalid input test
- [ ] Security test (injection, permissions)
- [ ] Performance test if applicable

```python
# Example test structure
def test_functionality_happy_path():
    """Test that functionality works with valid inputs."""
    # Arrange
    # Act
    # Assert

def test_functionality_error():
    """Test that it raises correct error with invalid inputs."""
    with pytest.raises(ExpectedError):
        # code that should fail

def test_functionality_edge_case():
    """Test edge cases (min values, max values, empty, etc)."""
    # Specific test
```

### 3.5 EXECUTE Tests and Show Results

**MANDATORY:** Execute tests and show results:

```bash
# Test execution
pytest tests/test_module.py -v

# Result:
# tests/test_module.py ✓ test_happy_path
# tests/test_module.py ✓ test_error_case
# tests/test_module.py ✓ test_edge_case
# tests/test_module.py ✓ test_security
#
# 4 passed, 0 failed, 0 skipped
```

**YOU MUST SHOW:**
- Total number of tests executed
- How many passed
- How many failed
- How many are pending

### 3.6 Validate Coverage and Quality

- Do all tests pass (100%)?
- Is estimated coverage ≥99%?
- Are there any uncovered cases?

If coverage < 99% or tests failing:

1. Identify what's missing
2. Improve code or tests
3. Repeat from 3.4 until ≥99% is reached

## PHASE 4: INTEGRAL VALIDATION WITH METRICS (after completing all tasks)

```markdown
## 📊 INTEGRAL VALIDATION REPORT

### 1. SECURITY VALIDATION
- [ ] No critical vulnerabilities
- [ ] Input validation on all endpoints
- [ ] Output sanitization
- [ ] No hardcoded secrets
- [ ] RBAC permissions correctly applied

### 2. TEST VALIDATION
- **Total tests executed:** [XX]
- **Tests passed:** [XX] (100%)
- **Tests failed:** [0]
- **Estimated coverage:** [≥99%]
- **Cases covered:** Happy path, error, edge cases, security

### 3. CODE QUALITY VALIDATION
- [ ] Type hints: 100% coverage
- [ ] Cyclomatic complexity < 10 per function
- [ ] No code duplication
- [ ] Semantic variable names
- [ ] Functions with single responsibility

### 4. PERFORMANCE VALIDATION
- [ ] No N+1 queries
- [ ] Adequate indexes on frequent queries
- [ ] Pagination in listings
- [ ] Timeouts configured

### 5. ARCHITECTURE VALIDATION
- [ ] No circular imports
- [ ] Layers respected
- [ ] Modules without undue coupling
```

## PHASE 5: REFINEMENT UNTIL ≥99%

If any metric doesn't reach 99%:

```markdown
## 🔄 REFINEMENT CYCLE

**Problem identified:** [description]
**Impact:** [high/medium/low]
**Corrective action:** [what I will do]
**Validation:** [how I will verify it's corrected]

**Executing correction...**
[Implement changes]

**Re-running tests...**
[Show results]

**Is coverage now ≥99%?** [YES/NO]
```

## PHASE 6: DELIVERY WITH TEST REPORT

```markdown
## ✅ FINAL DELIVERY

### Implementation summary
[2-3 lines describing what was implemented]

### Test report
- Total tests: XX
- Passed: XX (100%)
- Failed: 0
- Coverage: ≥99%

### Detailed execution
```
pytest tests/ -v
[Paste complete execution output]
```

### Key decisions
- [Decision 1]: [justification]
- [Decision 2]: [justification]

### Suggested next steps
1. [Next recommended task]
2. [Points of attention]
```

## ABSOLUTE RULES (NON-NEGOTIABLE)

### 1. MANDATORY TESTS
- Every function MUST have tests
- Tests MUST be executed and results shown
- Coverage MUST be ≥99%

### 2. SECURITY FIRST
- Never expose sensitive information
- Always validate inputs
- Always sanitize outputs

### 3. ZERO VULNERABILITIES
- No SQL injection
- No hardcoded secrets
- No sensitive data exposure

### 4. ZERO PRODUCTION BUGS
- Every line must have purpose
- Every function must have tests
- Every edge case must be considered
- ≥99% validation before delivery

### 5. TOTAL TRANSPARENCY
- Always show test results
- Explain technical decisions
- Ask when in doubt
- Report problems found

## MY SKILLS REPOSITORY

In the `.cursor/skills/` folder there may be skills that I should use when appropriate. Before each task, I must check if any skill applies.

## PERMANENT ACTIVATION

This method must be applied ALWAYS, for ALL tasks, without exception. It is my default way of working.
