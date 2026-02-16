# PDCA-T Enhanced Coding Method for Cursor AI

> **A systematic, quality-assured coding methodology that guarantees ≥99% test coverage and zero-production-bugs through rigorous validation cycles.**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Cursor Compatible](https://img.shields.io/badge/Cursor-AI-Compatible-blue)](https://cursor.sh)

**Author:** Francisco J Bernades  
**GitHub:** [@exchanet](https://github.com/exchanet)

---

## 🎯 Overview

The **PDCA-T Enhanced Coding Method** is a comprehensive workflow designed for AI-assisted development in Cursor. It transforms coding tasks into systematic, validated processes that ensure:

- ✅ **≥99% test coverage** on all code
- ✅ **Zero vulnerabilities** through security-first practices
- ✅ **Zero production bugs** via comprehensive edge case testing
- ✅ **Complete transparency** with detailed test reports
- ✅ **Systematic quality assurance** at every step

This method applies a **Plan-Do-Check-Act-Test (PDCA-T)** cycle enhanced with rigorous validation metrics, making it ideal for production-grade software development.

---

## 🚀 Quick Start

### Installation

1. **Clone or download this repository:**
   ```bash
   git clone https://github.com/exchanet/method_pdca-t_coding_Cursor.git
   cd method_pdca-t_coding_Cursor
   ```

2. **Copy the rule to your Cursor project:**
   ```bash
   # Copy the rule file
   cp .cursor/rules/METODO-PDCA-T.md /path/to/your/project/.cursor/rules/
   
   # Or copy the entire .cursor directory structure
   cp -r .cursor /path/to/your/project/
   ```

3. **The method will activate automatically** - Cursor will read the rule with `trigger: always_on` and apply it to all tasks.

### Alternative: Install as Skill

If you prefer to use it as a reusable skill:

```bash
cp -r .cursor/skills/metodo-pdca-t /path/to/your/project/.cursor/skills/
```

---

## 📖 The Method Explained

### Why This Method Works

Traditional coding workflows often skip validation or perform it as an afterthought. The PDCA-T method **integrates quality assurance at every step**, ensuring that:

1. **Planning prevents scope creep** - Clear objectives and requirements upfront
2. **Micro-tasks enable focus** - Maximum 50 lines per task ensures thoroughness
3. **Immediate validation catches errors early** - Tests written and executed before moving on
4. **99% coverage eliminates surprises** - Edge cases discovered during development, not production
5. **Security-first approach prevents vulnerabilities** - Input validation and output sanitization from day one

### The Complete Cycle

```
FASE 1: PLANIFICACIÓN (Planning)
│
▼
FASE 2: ANÁLISIS DE REQUISITOS (Requirements Analysis)
│
▼
FASE 3: DIVISIÓN EN MICRO-TAREAS (Micro-Task Division)
│
▼
┌─────────────────────────────────────────────────┐
│  FOR EACH MICRO-TASK:                          │
│  ┌─────────────────────────────────────────┐    │
│  │ 3.1 Check available skills              │    │
│  │ 3.2 Execute with applied skill          │    │
│  │ 3.3 Self-review                         │    │
│  │ 3.4 Generate COMPLETE tests              │    │
│  │ 3.5 EXECUTE tests and show results      │    │
│  │ 3.6 If coverage < 99% → refine & improve│    │
│  └─────────────────────────────────────────┘    │
└─────────────────────────────────────────────────┘
│
▼
FASE 4: VALIDACIÓN INTEGRAL CON MÉTRICAS (Integral Validation)
│
▼
FASE 5: REFINAMIENTO HASTA ≥99% (Refinement to ≥99%)
│
▼
FASE 6: ENTREGA CON REPORTE DE TESTS (Delivery with Test Report)
```

---

## 📚 Detailed Phase Breakdown

### Phase 1: Planning

**Purpose:** Establish clear understanding of what needs to be done.

**Actions:**
- Analyze the general objective
- Identify exact scope
- Ask clarifying questions if anything is unclear
- **Output:** Clear comprehension of the task

**Why it matters:** Without clear planning, you'll waste time fixing misunderstandings later. This phase ensures alignment from the start.

---

### Phase 2: Requirements Analysis

**Purpose:** Identify all functional and non-functional requirements, plus potential risks.

**Actions:**
- Identify functional requirements (what the code should do)
- Identify non-functional requirements (security, performance, scalability)
- Identify potential risks
- **Output:** Complete list of requirements and risks

**Why it matters:** Missing a non-functional requirement (like "must handle 10k requests/sec") leads to costly refactoring. This phase catches those early.

---

### Phase 3: Micro-Task Division

**Purpose:** Break work into manageable chunks of maximum 50 lines each.

**Why 50 lines?** 
- Easier to review thoroughly
- Easier to test completely
- Easier to debug if issues arise
- Forces modular, single-responsibility design

**For each micro-task, execute this sub-cycle:**

#### 3.1 Check Available Skills

Before writing code, check if there's a relevant skill in `.cursor/skills/` that can help. Skills provide specialized knowledge and workflows.

**Example:** If building a React component, check for `frontend-design` skill.

#### 3.2 Execute the Task

Write code following:
- Complete type hints (Python 3.12+ or TypeScript)
- Security best practices
- Zero hardcoding (everything configurable)
- Specific exception handling
- Structured logging

#### 3.3 Immediate Self-Review

Review the code you just wrote:
- ✅ Does it have type hints?
- ✅ Are there security vulnerabilities?
- ✅ Is there code duplication?
- ✅ Is it readable and maintainable?
- ✅ Does it follow language best practices?

**Why immediate?** Catching issues right after writing is 10x easier than days later.

#### 3.4 Generate Complete Tests

Write unit tests covering:

**Minimum Required:**
- [ ] Happy path test (normal operation)
- [ ] Error case test (validation, exceptions)
- [ ] Edge case test (boundary conditions)
- [ ] Boundary value test
- [ ] Invalid input test
- [ ] Security test (injection, permissions)
- [ ] Performance test (if applicable)

**Example Structure:**
```python
def test_functionality_happy_path():
    """Test that functionality works with valid inputs."""
    # Arrange
    input_data = create_valid_input()
    # Act
    result = functionality(input_data)
    # Assert
    assert result.is_valid()
    assert result.value == expected_value

def test_functionality_error():
    """Test that it raises correct error with invalid inputs."""
    with pytest.raises(ValidationError):
        functionality(invalid_input)

def test_functionality_edge_case():
    """Test edge cases (min values, max values, empty, etc)."""
    # Test empty input
    result = functionality(empty_input)
    assert result == default_value
```

#### 3.5 Execute Tests and Show Results

**MANDATORY:** Execute tests and display:
- Total number of tests executed
- How many passed
- How many failed
- How many are pending

**Example Output:**
```bash
$ pytest tests/test_module.py -v

tests/test_module.py::test_happy_path PASSED
tests/test_module.py::test_error_case PASSED
tests/test_module.py::test_edge_case PASSED
tests/test_module.py::test_security PASSED

4 passed, 0 failed, 0 skipped
```

**Why show results?** Transparency builds trust and helps identify issues immediately.

#### 3.6 Validate Coverage and Quality

- Do all tests pass (100%)?
- Is estimated coverage ≥99%?
- Are there any uncovered cases?

**If coverage < 99% or tests failing:**
1. Identify what's missing
2. Improve code or tests
3. Repeat from 3.4 until ≥99% is reached

**Why 99%?** 100% is often impractical (error handlers, unreachable code), but 99% ensures all critical paths are tested.

---

### Phase 4: Integral Validation with Metrics

After completing all micro-tasks, generate a comprehensive report:

#### 1. Security Validation
- [ ] No critical vulnerabilities
- [ ] Input validation on all endpoints
- [ ] Output sanitization
- [ ] No hardcoded secrets
- [ ] RBAC permissions correctly applied

#### 2. Test Validation
- **Total tests executed:** [XX]
- **Tests passed:** [XX] (100%)
- **Tests failed:** [0]
- **Estimated coverage:** [≥99%]
- **Cases covered:** Happy path, error, edge cases, security

#### 3. Code Quality Validation
- [ ] Type hints: 100% coverage
- [ ] Cyclomatic complexity < 10 per function
- [ ] No code duplication
- [ ] Semantic variable names
- [ ] Functions with single responsibility

#### 4. Performance Validation
- [ ] No N+1 queries
- [ ] Adequate indexes on frequent queries
- [ ] Pagination in listings
- [ ] Timeouts configured

#### 5. Architecture Validation
- [ ] No circular imports
- [ ] Layers respected
- [ ] Modules without undue coupling

---

### Phase 5: Refinement to ≥99%

If any metric doesn't reach 99%:

1. **Identify the problem** - What's missing?
2. **Assess impact** - High/Medium/Low
3. **Define corrective action** - What will you do?
4. **Implement correction** - Make the changes
5. **Re-run tests** - Verify the fix
6. **Confirm coverage ≥99%** - Goal achieved?

**Why iterate?** Perfection isn't achieved on the first try. This phase ensures you reach the quality bar.

---

### Phase 6: Delivery with Test Report

Generate a final report with:

- **Implementation Summary** (2-3 lines describing what was implemented)
- **Test Report:**
  - Total tests: XX
  - Passed: XX (100%)
  - Failed: 0
  - Coverage: ≥99%
- **Detailed Execution** (complete pytest output)
- **Key Decisions** (with justifications)
- **Suggested Next Steps**

**Why document decisions?** Future developers (including yourself) will understand why choices were made.

---

## 🔒 Absolute Rules (Non-Negotiable)

### 1. Mandatory Tests
- Every function MUST have tests
- Tests MUST be executed and results shown
- Coverage MUST be ≥99%

### 2. Security First
- Never expose sensitive information
- Always validate inputs
- Always sanitize outputs

### 3. Zero Vulnerabilities
- No SQL injection
- No hardcoded secrets
- No sensitive data exposure

### 4. Zero Production Bugs
- Every line must have purpose
- Every function must have tests
- Every edge case must be considered
- ≥99% validation before delivery

### 5. Total Transparency
- Always show test results
- Explain technical decisions
- Ask when in doubt
- Report problems found

---

## 📁 Repository Structure

```
method_pdca-t_coding_Cursor/
├── .cursor/
│   ├── rules/
│   │   └── METODO-PDCA-T.md          # Cursor rule (auto-activates)
│   └── skills/
│       └── metodo-pdca-t/
│           └── SKILL.md              # Reusable skill
├── docs/
│   ├── INSTALLATION.md               # Installation guide
│   ├── USAGE.md                      # Usage examples
│   └── PHASES.md                     # Detailed phase explanations
├── examples/
│   └── example-implementation.md    # Real-world examples
├── README.md                         # This file (English)
├── README.es.md                      # Spanish version
├── LICENSE                           # MIT License
└── CONTRIBUTING.md                   # Contribution guidelines
```

---

## 🎓 Examples

See the [`examples/`](./examples/) directory for real-world implementation examples.

### Example: Implementing a Tax Calculator

```
FASE 1: Planning
→ Objective: Create tax calculation function

FASE 2: Requirements Analysis
→ Functional: Calculate VAT, income tax
→ Non-functional: Decimal precision, performance
→ Risks: Rounding errors, negative values

FASE 3: Micro-tasks
→ Task 1: calculate_vat function (50 lines)
  → 3.1: Check skills (none applicable)
  → 3.2: Implement function
  → 3.3: Self-review ✓
  → 3.4: Generate tests (happy path, error, edge cases)
  → 3.5: Execute tests → 5 passed
  → 3.6: Coverage 100% ✓

→ Task 2: calculate_income_tax function (50 lines)
  → [same cycle]

FASE 4: Integral Validation
→ Security: ✓ Input validation
→ Tests: 10 passed, 0 failed, coverage 100%
→ Quality: ✓ Complete type hints
→ Performance: ✓ No issues
→ Architecture: ✓ No coupling

FASE 5: Refinement
→ Not needed (already ≥99%)

FASE 6: Delivery
→ [Complete report]
```

---

## 🤝 Contributing

Contributions are welcome! Please read [CONTRIBUTING.md](./CONTRIBUTING.md) for details on our code of conduct and the process for submitting pull requests.

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details.

---

## 🙏 Acknowledgments

- Inspired by PDCA (Plan-Do-Check-Act) methodology
- Enhanced with Test-Driven Development principles
- Designed for AI-assisted development in Cursor

---

## 📞 Contact

**Author:** Francisco J Bernades  
**GitHub:** [@exchanet](https://github.com/exchanet)

For questions, suggestions, or feedback, please open an issue on GitHub.

---

## ⭐ Why This Method Delivers Excellent Results

### 1. **Prevents Technical Debt**
By requiring tests and validation at every step, you catch issues early when they're cheap to fix.

### 2. **Ensures Security**
Security-first approach means vulnerabilities are prevented, not patched later.

### 3. **Builds Confidence**
When you see "100% tests passed, 99% coverage," you know the code works.

### 4. **Facilitates Maintenance**
Well-tested, well-documented code is easier to modify and extend.

### 5. **Scales with Complexity**
The micro-task approach keeps complexity manageable even for large features.

### 6. **Transparency**
Complete test reports and decision documentation help teams collaborate effectively.

---

**Ready to code with confidence?** Install the method and start your next task! 🚀
