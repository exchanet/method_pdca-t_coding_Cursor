# PDCA-T Enhanced Method with ≥99% Validation

Systematic working method for software development with ≥99% quality guarantee through enhanced PDCA-T cycle.

## When to use this skill

This skill should be activated automatically for ALL development tasks, without exception. It defines the standard workflow for the agent.

## The Complete Method

### Enhanced PDCA-T Cycle

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

## Detailed Phases

### PHASE 1: INITIAL PLANNING

**Objective:** Clearly understand what needs to be done.

**Actions:**
- Analyze the general objective
- Identify the exact scope
- Ask if something is unclear
- **Output:** Clear understanding of what needs to be done

### PHASE 2: REQUIREMENTS ANALYSIS

**Objective:** Identify all requirements and risks.

**Actions:**
- Identify functional requirements
- Identify non-functional requirements (security, performance, scalability)
- Identify potential risks
- **Output:** List of requirements and risks

### PHASE 3: MICRO-TASK DIVISION

**Objective:** Divide work into manageable tasks of maximum 50 lines each.

**Actions:**
- Divide work into micro-tasks
- Each micro-task must be independent and testable
- Execute the sub-cycle for each micro-task:

#### 3.1 Check Available Skills
- Check if there are applicable skills in `.cursor/skills/`
- If a relevant skill exists, use it automatically
- If not, execute with general best practices

#### 3.2 Execute the Task
- Complete type hints (Python 3.12+ or TypeScript)
- Security best practices
- Zero hardcoding (everything configurable)
- Specific exception handling
- Structured logging

#### 3.3 Immediate Self-Review
- Verify type hints
- Review security vulnerabilities
- Detect code duplication
- Evaluate readability and maintainability
- Confirm language best practices

#### 3.4 Generate COMPLETE Tests

**Minimum required:**
- [ ] Happy path test
- [ ] Error case test (validation, exceptions)
- [ ] Edge case test
- [ ] Boundary value test
- [ ] Invalid input test
- [ ] Security test (injection, permissions)
- [ ] Performance test if applicable

#### 3.5 EXECUTE Tests and Show Results

**MANDATORY:** Execute tests and show:
- Total number of tests executed
- How many passed
- How many failed
- How many are pending

#### 3.6 Validate Coverage and Quality

- Do all tests pass (100%)?
- Is estimated coverage ≥99%?
- Are there any uncovered cases?

If coverage < 99% or tests failing:
1. Identify what's missing
2. Improve code or tests
3. Repeat from 3.4 until ≥99% is reached

### PHASE 4: INTEGRAL VALIDATION WITH METRICS

After completing all micro-tasks, generate a report with:

1. **Security Validation**
   - No critical vulnerabilities
   - Input validation on all endpoints
   - Output sanitization
   - No hardcoded secrets
   - RBAC permissions correctly applied

2. **Test Validation**
   - Total tests executed
   - Tests passed (100%)
   - Tests failed (0)
   - Estimated coverage (≥99%)
   - Cases covered: Happy path, error, edge cases, security

3. **Code Quality Validation**
   - Type hints: 100% coverage
   - Cyclomatic complexity < 10 per function
   - No code duplication
   - Semantic variable names
   - Functions with single responsibility

4. **Performance Validation**
   - No N+1 queries
   - Adequate indexes on frequent queries
   - Pagination in listings
   - Timeouts configured

5. **Architecture Validation**
   - No circular imports
   - Layers respected
   - Modules without undue coupling

### PHASE 5: REFINEMENT UNTIL ≥99%

If any metric doesn't reach 99%:

1. Identify the problem
2. Assess impact (high/medium/low)
3. Define corrective action
4. Implement the correction
5. Re-run tests
6. Verify that coverage ≥99%

### PHASE 6: DELIVERY WITH TEST REPORT

Generate a final report with:

- **Implementation Summary** (2-3 lines)
- **Test Report:**
  - Total tests: XX
  - Passed: XX (100%)
  - Failed: 0
  - Coverage: ≥99%
- **Detailed Execution** (complete pytest output)
- **Key Decisions** (with justifications)
- **Suggested Next Steps**

## Absolute Rules

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

## Usage Examples

### Example 1: Implement New Function

```
PHASE 1: Planning
→ Objective: Create tax calculation function

PHASE 2: Requirements Analysis
→ Functional requirements: Calculate VAT, income tax
→ Non-functional requirements: Decimal precision, performance
→ Risks: Rounding errors, negative values

PHASE 3: Micro-tasks
→ Task 1: calculate_vat function (50 lines)
  → 3.1: Check skills (none applicable)
  → 3.2: Implement function
  → 3.3: Self-review
  → 3.4: Generate tests (happy path, error, edge cases)
  → 3.5: Execute tests → 5 passed
  → 3.6: Coverage 100% ✓

→ Task 2: calculate_income_tax function (50 lines)
  → [same cycle]

PHASE 4: Integral Validation
→ Security: ✓ Input validation
→ Tests: 10 passed, 0 failed, coverage 100%
→ Quality: ✓ Complete type hints
→ Performance: ✓ No issues
→ Architecture: ✓ No coupling

PHASE 5: Refinement
→ Not needed (already ≥99%)

PHASE 6: Delivery
→ [Complete report]
```

## Important Notes

- This method must be applied ALWAYS, without exception
- If a project doesn't have pytest configured, propose alternatives maintaining the same rigor
- 99% coverage is a goal; if impossible to reach, document why and propose alternatives
- Transparency is key: always show test results and explain decisions
