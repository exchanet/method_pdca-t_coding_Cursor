# 🔁 Method PDCA-T — AI Coding Quality Framework

> **A systematic, multi-agent quality methodology for AI-assisted development that guarantees ≥99% test coverage, zero vulnerabilities, zero production bugs, and fully documented delivery.**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Version](https://img.shields.io/badge/version-3.0.0-blue.svg)]()
[![Agent: Any](https://img.shields.io/badge/agent-any-green.svg)]()
[![Language: ES/EN](https://img.shields.io/badge/Language-ES%2FEN-blue.svg)](./README_ES.md)

**Original Author:** Francisco J. Bernades ([@exchanet](https://github.com/exchanet))  
**Repository:** [github.com/exchanet/method_pdca-t_coding](https://github.com/exchanet/method_pdca-t_coding)

---

> ⚠️ **Want complete production-grade systems?**  
> Method PDCA-T handles quality, testing, and systematic validation.  
> For modular architecture with auto-generated Admin Panels, use it alongside **[Method Modular Design](https://github.com/exchanet/method_modular_design)**.  
> *Modular Design builds the right system. PDCA-T builds it right.*

---

## 🎯 What Does Method PDCA-T Do?

Method PDCA-T instructs any AI coding agent to follow a rigorous quality cycle where:

- ✅ **Architecture is designed before code** — ADRs and interface contracts first
- ✅ **Tests are written before implementation** — strict TDD, not optional
- ✅ **Every micro-task ≤ 50 lines** — focused, reviewable, single-responsibility
- ✅ **Coverage ≥ 99% mandatory** — enforced before any delivery
- ✅ **Technical debt is tracked** — registered, prioritized, planned
- ✅ **Every delivery has a full report** — tests, decisions, CI/CD checklist
- ✅ **Works with any agent** — Cursor, Windsurf, GitHub Copilot, Claude Code, Claude.ai, ChatGPT, Aider
- ✅ **Works with any stack** — Python, Node.js, Go, TypeScript, any language

---

## 🚀 Quick Start

### Install — 3 options

**Option 1 — enet (recommended)**

[`enet`](https://github.com/exchanet/enet) is the exchanet methods manager. Detects your AI agent automatically and installs the adapter in the right place.

```bash
npm install -g @exchanet/enet
enet install pdca-t
```

**Option 2 — enet via GitHub (no npm account needed)**

```bash
npm install -g github:exchanet/enet
enet install pdca-t
```

**Option 3 — Manual**

Download the adapter for your agent from the `adapters/` folder:

| Agent | File | Place at |
|-------|------|----------|
| Cursor | `adapters/cursor.md` | `.cursor/rules/method-pdca-t.md` |
| Windsurf | `adapters/windsurf.md` | Append to `.windsurfrules` |
| GitHub Copilot | `adapters/copilot.md` | `.github/copilot-instructions.md` |
| Claude Code | `adapters/claudecode.md` | `CLAUDE.md` |
| Claude.ai | `adapters/claudeai.md` | Paste into system prompt or conversation |
| ChatGPT / GPT-4 | `adapters/openai.md` | Paste into custom instructions |
| Aider | `adapters/aider.md` | `--system-prompt` flag or `.aider.conf.yml` |
| Any other agent | `adapters/generic.md` | Paste into your agent's context |

---

## 📖 The Method Explained

### Why PDCA-T Works

Traditional AI-assisted coding skips validation or treats it as an afterthought. PDCA-T **integrates quality assurance at every step**:

1. **Planning prevents scope creep** — Clear objectives before a single line of code
2. **Architecture first** — Decisions documented before implementation begins
3. **TDD by default** — Tests written before code, not after
4. **Micro-tasks enable focus** — ≤ 50 lines per task ensures thoroughness
5. **Immediate validation catches errors early** — Never discover bugs in production
6. **Debt tracking prevents accumulation** — Known issues are visible, not buried
7. **Security-first** — Input validation and output sanitization from day one

---

## 🔄 The Complete 8-Phase Cycle

```
PHASE 1: PLANNING
│  → Clear objective · exact scope · questions resolved · success criteria
│
PHASE 2: REQUIREMENTS ANALYSIS
│  → Functional requirements · Non-functional requirements · Risks
│
PHASE 3: ARCHITECTURE DESIGN  ★ NEW
│  → ADRs · Interface contracts · Module structure
│
PHASE 4: MICRO-TASK CYCLE (for each task ≤ 50 lines)
│  ┌────────────────────────────────────────────────┐
│  │ 4.1 Check available skills and context         │
│  │ 4.2 Write tests FIRST (strict TDD)             │
│  │ 4.3 Implement code (≤ 50 lines)                │
│  │ 4.4 Self-review checklist                      │
│  │ 4.5 Execute tests — show REAL results          │
│  │ 4.6 If coverage < 99% → refine and repeat      │
│  └────────────────────────────────────────────────┘
│
PHASE 5: INTEGRAL VALIDATION WITH METRICS
│  → Security · Tests · Code quality · Performance · Architecture
│
PHASE 6: TECHNICAL DEBT MANAGEMENT  ★ NEW
│  → Register · Prioritize · Plan
│
PHASE 7: REFINEMENT TO ≥ 99%
│  → Identify → Fix → Verify → Confirm
│
PHASE 8: DELIVERY WITH FULL REPORT
│  → Summary · Tests · Decisions · CI/CD checklist · Next steps
```

---

## 📋 Phase Detail

### Phase 1: Planning

**Output:** Unambiguous understanding of what needs to be built.

Actions:
- Analyze the general objective with precision
- Identify exact scope (what IS and IS NOT included)
- Ask clarifying questions before writing code
- Identify external dependencies (APIs, libraries, services)
- Define the success criteria for delivery

```
Questions to answer before proceeding:
  What exactly should this code do?
  Who will use it and in what context?
  What is explicitly OUT of scope?
  What already exists that can be reused?
  What is the acceptance criterion?
```

---

### Phase 2: Requirements Analysis

**Output:** Complete list of RF + RNF + identified risks.

```
Functional Requirements (FR):
  FR-01: Calculate VAT at 21% on base price
  FR-02: Handle prices with up to 4 decimals
  FR-03: Return error if price is negative

Non-Functional Requirements (NFR):
  NFR-01: Response time < 100ms for single calculations
  NFR-02: Decimal precision using Decimal, not float
  NFR-03: Thread-safe for concurrent use

Risk Register:
  RISK-01: Float rounding errors → Mitigation: use Decimal
  RISK-02: Overflow with large prices → Mitigation: validate limits
```

---

### Phase 3: Architecture Design ★ NEW

**Output:** ADRs + interface contracts + module structure.

Document Architecture Decision Records (ADRs) **before** writing implementations:

```markdown
## ADR-001: Decimal precision library
- Context: Financial calculations require exact precision
- Decision: Use native Python decimal.Decimal
- Alternatives: float (rejected — imprecision), mpmath (overkill)
- Consequences: More verbose, but correct
```

Define interface contracts before implementing:

```python
def calculate_vat(
    base_price: Decimal,
    vat_rate: Decimal = Decimal("0.21"),
    currency: str = "EUR"
) -> VATResult:
    """
    Calculate VAT on a base price.

    Args:
        base_price: Pre-tax price (must be > 0)
        vat_rate: VAT rate as decimal (0.21 = 21%)
        currency: ISO currency code

    Returns:
        VATResult with base, vat_amount and total

    Raises:
        ValueError: If base_price <= 0
        ValueError: If vat_rate not in [0, 1]
    """
    ...
```

Recommended module structure:
```
src/
├── domain/          # Pure business logic (no external deps)
│   ├── models.py
│   └── services.py
├── infrastructure/  # External adapters (DB, APIs, etc.)
└── interfaces/      # Controllers, CLI, API endpoints

tests/
├── unit/            # Tests with no I/O
├── integration/     # Tests with real infrastructure
└── e2e/             # End-to-end flow tests
```

---

### Phase 4: Micro-Task Cycle

**Rule:** ≤ 50 lines per micro-task. One responsibility. Fully testable.

#### 4.2 — Write Tests FIRST (Mandatory TDD)

```python
# tests/unit/test_vat_calculator.py
class TestCalculateVAT:

    # HAPPY PATH
    def test_standard_vat_calculation(self):
        result = calculate_vat(Decimal("100.00"))
        assert result.base == Decimal("100.00")
        assert result.vat_amount == Decimal("21.00")
        assert result.total == Decimal("121.00")

    # ERROR CASES
    def test_negative_price_raises_error(self):
        with pytest.raises(ValueError, match="base_price must be positive"):
            calculate_vat(Decimal("-10.00"))

    def test_invalid_vat_rate_raises_error(self):
        with pytest.raises(ValueError, match="vat_rate must be between 0 and 1"):
            calculate_vat(Decimal("100.00"), vat_rate=Decimal("1.5"))

    # EDGE CASES
    def test_minimum_valid_price(self):
        result = calculate_vat(Decimal("0.0001"))
        assert result.base == Decimal("0.0001")

    def test_zero_vat_rate(self):
        result = calculate_vat(Decimal("100.00"), vat_rate=Decimal("0"))
        assert result.vat_amount == Decimal("0")

    # SECURITY
    def test_type_validation_rejects_float(self):
        with pytest.raises(TypeError):
            calculate_vat(10.0)  # float not accepted

    # PERFORMANCE
    def test_bulk_calculation_performance(self, benchmark):
        prices = [Decimal(str(i)) for i in range(1, 10001)]
        benchmark(lambda: [calculate_vat(p) for p in prices])
```

#### 4.3 — Implement the Code (≤ 50 lines)

```python
# src/domain/services.py
from decimal import Decimal
from dataclasses import dataclass

@dataclass(frozen=True)
class VATResult:
    base: Decimal
    vat_amount: Decimal
    total: Decimal
    currency: str

def calculate_vat(
    base_price: Decimal,
    vat_rate: Decimal = Decimal("0.21"),
    currency: str = "EUR"
) -> VATResult:
    if not isinstance(base_price, Decimal):
        raise TypeError("base_price must be Decimal, not float")
    if base_price <= Decimal("0"):
        raise ValueError("base_price must be positive")
    if not Decimal("0") <= vat_rate <= Decimal("1"):
        raise ValueError("vat_rate must be between 0 and 1")

    vat_amount = base_price * vat_rate
    return VATResult(
        base=base_price,
        vat_amount=vat_amount,
        total=base_price + vat_amount,
        currency=currency
    )
```

#### 4.4 — Self-Review Checklist

```
CODE QUALITY:
  □ Complete type hints on all functions?
  □ Docstring explaining the contract?
  □ Single responsibility per function?
  □ Semantic names (no a, b, x)?
  □ No unnecessary code duplication?

SECURITY:
  □ ALL inputs validated?
  □ Outputs sanitized before display?
  □ No hardcoded credentials?
  □ Safe types used (Decimal instead of float for money)?

MAINTAINABILITY:
  □ Can another dev understand this in 2 minutes?
  □ Consistent abstraction level?
  □ Errors logged appropriately?
```

#### 4.5 — Execute Tests and Show Results

**MANDATORY:** Always show the complete real output.

```bash
$ pytest tests/unit/test_vat_calculator.py -v --cov=src --cov-report=term-missing

tests/unit/test_vat_calculator.py::TestCalculateVAT::test_standard_vat_calculation PASSED
tests/unit/test_vat_calculator.py::TestCalculateVAT::test_negative_price_raises_error PASSED
tests/unit/test_vat_calculator.py::TestCalculateVAT::test_invalid_vat_rate_raises_error PASSED
tests/unit/test_vat_calculator.py::TestCalculateVAT::test_minimum_valid_price PASSED
tests/unit/test_vat_calculator.py::TestCalculateVAT::test_zero_vat_rate PASSED
tests/unit/test_vat_calculator.py::TestCalculateVAT::test_type_validation_rejects_float PASSED
tests/unit/test_vat_calculator.py::TestCalculateVAT::test_bulk_calculation_performance PASSED

Name                    Stmts   Miss  Cover
-------------------------------------------
src/domain/services.py     14      0   100%
-------------------------------------------
TOTAL                       14      0   100%

7 passed in 0.43s
```

---

### Phase 5: Integral Validation with Metrics

| Dimension | Checklist |
|-----------|-----------|
| **Security** | No critical vulnerabilities (OWASP Top 10) · Input validation · Output sanitization · No hardcoded secrets · Minimum privilege |
| **Tests** | 100% passed · 0 failed · Coverage ≥ 99% · Happy path + Error + Edge + Security covered |
| **Code Quality** | Type hints: 100% · Cyclomatic complexity < 10 · No duplication · Semantic names · SRP |
| **Performance** | No N+1 queries · Indexes on frequent fields · Pagination in listings · Timeouts configured |
| **Architecture** | No circular imports · Layers respected · Low coupling · Well-defined interfaces |

---

### Phase 6: Technical Debt Management ★ NEW

Do not ignore technical debt — register, prioritize, and plan it.

```markdown
## DEBT-001
- Type: Technical (code)
- Description: calculate_vat does not support multi-currency conversion
- Impact: Medium — works correctly for single currency
- Estimated effort: 2 hours
- Priority: Low — not blocking for v1.0
- Plan: Implement in v1.1 with exchange rate service
```

Types to register:
- **Technical debt:** Code that works but is below standard
- **Test debt:** Missing or insufficient tests
- **Documentation debt:** Unexplained code
- **Architecture debt:** Suboptimal decisions that scale poorly

---

### Phase 7: Refinement to ≥ 99%

```
If any metric does not reach 99%:

1. IDENTIFY   — What specifically is below 99%?
2. CLASSIFY   — High / Medium / Low priority
3. PLAN       — What action will fix the problem?
4. EXECUTE    — Implement the correction
5. VERIFY     — Re-run all tests
6. CONFIRM    — ≥ 99% now? If not → back to step 1

⚠ Never advance to delivery without confirming ≥ 99%.
```

---

### Phase 8: Delivery with Full Report

```markdown
# Delivery Report — [Feature Name]
Date: YYYY-MM-DD
Implemented by: [AI Agent + human reviewer]
Version: X.Y.Z

## Implementation Summary
[2-3 sentences describing what was implemented and how]

## Test Report
| Category      | Result    |
|---------------|-----------|
| Total tests   | XX        |
| Passed        | XX (100%) |
| Failed        | 0         |
| Coverage      | ≥ 99%     |
| Total time    | X.XXs     |

## Full pytest Output
[Paste real pytest output here]

## Key Technical Decisions
1. [Decision]: [Brief justification]
2. [Decision]: [Brief justification]

## Technical Debt Registered
- DEBT-001: [description] — Priority: Low

## CI/CD Checklist
  □ Tests pass in pipeline
  □ Linting without errors
  □ Type checking without errors
  □ Security scan without critical vulnerabilities

## Suggested Next Steps
1. [What comes next in the backlog]
2. [Dependencies this unlocks]
```

---

## 🔒 Absolute Rules (Non-Negotiable)

```
RULE 1 — Tests are mandatory
  ✗ "Tests will be added later"
  ✓ Tests written BEFORE implementation code

RULE 2 — Show real results
  ✗ "Tests should pass"
  ✓ Real pytest output with exact numbers

RULE 3 — Security first
  ✗ Hardcode secrets "for now"
  ✓ Environment variables / vault from the first commit

RULE 4 — Coverage ≥ 99% or no delivery
  ✗ Deliver with 85% coverage and "almost complete"
  ✓ Iterate until ≥ 99% before marking as delivered

RULE 5 — Document decisions
  ✗ "The code is self-explanatory"
  ✓ ADRs for non-trivial decisions, docstrings for everything public

RULE 6 — Register debt  ★ NEW
  ✗ Ignore known problems "for later"
  ✓ Register in DEBT-XXX format with priority and plan
```

---

## 🤖 Multi-Agent Support ★ NEW

Method PDCA-T v3.0 includes adapters for every major AI coding agent:

| Agent | Adapter | Notes |
|-------|---------|-------|
| **Cursor** | `adapters/cursor.md` | Rule with `trigger: always_on` |
| **Windsurf** | `adapters/windsurf.md` | Appended to `.windsurfrules` |
| **GitHub Copilot** | `adapters/copilot.md` | Placed in `.github/copilot-instructions.md` |
| **Claude Code** | `adapters/claudecode.md` | Placed in `CLAUDE.md` |
| **Claude.ai** | `adapters/claudeai.md` | Paste into system prompt or conversation |
| **ChatGPT / GPT-4o** | `adapters/openai.md` | Paste into custom instructions |
| **Google Antigravity** | `adapters/antigravity.md` | `.agent/rules/method-pdca-t.md` |
| **Google Antigravity** | `adapters/antigravity.md` | `.agent/rules/method-pdca-t.md` |
| **Aider** | `adapters/aider.md` | `--system-prompt` or `.aider.conf.yml` |
| **Any other agent** | `adapters/generic.md` | Paste into your agent's context |

Each adapter is tuned to how that specific agent reads and applies instructions — same method, optimized per agent.

---

## 🛠️ Recommended CI/CD Configuration ★ NEW

```yaml
# .github/workflows/quality.yml
name: PDCA-T Quality Gate

on: [push, pull_request]

jobs:
  quality:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Setup Python
        uses: actions/setup-python@v5
        with:
          python-version: "3.11"

      - name: Install dependencies
        run: pip install -r requirements.txt

      - name: Lint (ruff)
        run: ruff check src/ tests/

      - name: Type check (mypy)
        run: mypy src/

      - name: Security scan (bandit)
        run: bandit -r src/ -ll

      - name: Tests with coverage gate
        run: |
          pytest tests/ \
            --cov=src \
            --cov-fail-under=99 \
            --cov-report=xml \
            -v

      - name: Upload coverage
        uses: codecov/codecov-action@v4
```

---

## 📁 Repository Structure

```
method_pdca-t/
├── METHOD.md                        ← Full method documentation
├── README.md                        ← This file (English)
├── README_ES.md                     ← Spanish version
│
├── adapters/
│   ├── cursor.md                    ← Cursor
│   ├── windsurf.md                  ← Windsurf
│   ├── copilot.md                   ← GitHub Copilot
│   ├── claudecode.md                ← Claude Code
│   ├── claudeai.md                  ← Claude.ai
│   ├── openai.md                    ← ChatGPT / GPT-4o
│   ├── aider.md                     ← Aider
│   └── generic.md                   ← Any other agent
│
├── .cursor/
│   ├── rules/
│   │   └── METHOD-PDCA-T.md         ← Cursor auto-activation rule
│   └── skills/
│       └── method-pdca-t/
│           └── SKILL.md
│
├── templates/
│   ├── delivery-report.md           ← Delivery report template
│   ├── adr-template.md              ← Architecture decision record
│   └── debt-register.md             ← Technical debt register
│
├── examples/
│   ├── tax-calculator/              ← Full worked example
│   └── rest-api/                    ← REST API example
│
├── docs/
│   ├── INSTALLATION.md
│   └── USAGE.md
│
├── .github/
│   └── workflows/
│       └── quality.yml              ← CI/CD pipeline
│
├── CHANGELOG.md
├── CONTRIBUTING.md
└── LICENSE
```

---

## 📊 Quality Targets at a Glance

| Metric | Target |
|--------|--------|
| Test coverage | ≥ 99% |
| Tests failed | 0 |
| Lines per micro-task | ≤ 50 |
| Cyclomatic complexity | < 10 per function |
| Hardcoded secrets | 0 |
| Type hint coverage (public) | 100% |

---

## 🆚 What Changed in v3.0

| Aspect | v1.0 Original | v3.0 Improved |
|--------|--------------|---------------|
| Phases | 6 | 8 |
| Architecture design phase | ❌ | ✅ Phase 3 with ADRs |
| Explicit TDD | Partial | ✅ Tests BEFORE code |
| Technical debt management | ❌ | ✅ Phase 6 with DEBT-XXX format |
| CI/CD pipeline | ❌ | ✅ GitHub Actions included |
| Architecture Decision Records | ❌ | ✅ Template included |
| Test types | Basic unit | ✅ Unit + Integration + E2E |
| Multi-agent adapters | Cursor only | ✅ 8 agents supported |
| Delivery report | Basic | ✅ Complete with CI/CD checklist |
| Technical debt templates | ❌ | ✅ Full template included |
| enet CLI installation | ❌ | ✅ `enet install pdca-t` |

---

## 📖 Related Methods

Method PDCA-T works best alongside:

- **[Method Modular Design](https://github.com/exchanet/method_modular_design)** ⭐ Recommended — Clean modular architecture with auto-generated Admin Panel. *Modular Design builds the right system. PDCA-T builds it right.*
- **[Method IRIS](https://github.com/exchanet/method_IRIS)** — Continuous improvement of existing systems.
- **[Method Enterprise Builder](https://github.com/exchanet/method_enterprise_builder_planning)** — Large-scale planning for complex projects.

---

## 🌐 Read in Spanish

**📖 [Leer en Español](./README_ES.md)**

---

## 🤝 Contributing

Contributions are welcome. New adapter examples, stack-specific templates, and real project demos are especially appreciated.

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/improvement`)
3. Commit your changes
4. Push and open a Pull Request

---

## 📄 License

MIT — Free to use, modify, and distribute with attribution.

---

## 👤 Author

**Francisco J. Bernades**

- GitHub: [@exchanet](https://github.com/exchanet)
- Repository: [github.com/exchanet/method_pdca-t_coding](https://github.com/exchanet/method_pdca-t_coding)

---

*"Coding with AI is no different from coding in a team — process discipline is what separates the prototype from production software."*
