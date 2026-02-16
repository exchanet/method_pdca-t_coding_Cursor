# Usage Guide

Practical examples and use cases for the PDCA-T Enhanced Coding Method.

**Author:** Francisco J Bernades  
**GitHub:** [@exchanet](https://github.com/exchanet)

---

## 📖 Table of Contents

- [Basic Usage](#basic-usage)
- [Real-World Examples](#real-world-examples)
- [Best Practices](#best-practices)
- [Common Patterns](#common-patterns)
- [Troubleshooting](#troubleshooting)

---

## 🚀 Basic Usage

### Starting a New Task

When you start a coding task in Cursor, the PDCA-T method will automatically:

1. **Plan** - Understand the objective
2. **Analyze Requirements** - Identify functional and non-functional requirements
3. **Divide into Micro-Tasks** - Break down into ≤50 line chunks
4. **Execute with Validation** - Code, test, and validate each micro-task
5. **Integral Validation** - Comprehensive quality check
6. **Refinement** - Iterate until ≥99% coverage
7. **Delivery** - Final report with test results

### Example: Simple Function Implementation

**Task:** "Create a function to calculate the area of a circle"

**What happens:**

```
FASE 1: PLANIFICACIÓN
→ Objective: Create calculate_circle_area function
→ Scope: Single function, takes radius, returns area
→ Clarifications: None needed

FASE 2: ANÁLISIS DE REQUISITOS
→ Functional: Calculate area using π * r²
→ Non-functional: Handle negative/zero inputs, precision
→ Risks: Division by zero, invalid input types

FASE 3: MICRO-TAREAS
→ Task 1: Implement calculate_circle_area (30 lines)
  → 3.1: Check skills (none applicable)
  → 3.2: Write function with type hints, validation
  → 3.3: Self-review ✓
  → 3.4: Generate tests:
    - test_happy_path: radius = 5 → area ≈ 78.54
    - test_error_negative: radius = -1 → ValueError
    - test_error_zero: radius = 0 → ValueError
    - test_error_type: radius = "5" → TypeError
    - test_precision: radius = 1 → area ≈ 3.14159
  → 3.5: Execute tests → 5 passed
  → 3.6: Coverage 100% ✓

FASE 4: VALIDACIÓN INTEGRAL
→ Security: ✓ Input validation
→ Tests: 5 passed, 0 failed, coverage 100%
→ Quality: ✓ Type hints complete
→ Performance: ✓ No issues
→ Architecture: ✓ No coupling

FASE 5: REFINAMIENTO
→ Not needed (already ≥99%)

FASE 6: ENTREGA
→ Function implemented with 100% test coverage
→ All edge cases handled
→ Ready for production
```

---

## 💼 Real-World Examples

### Example 1: API Endpoint Implementation

**Task:** "Create a REST API endpoint to get user profile"

**Implementation Flow:**

```
FASE 1: PLANIFICACIÓN
→ Objective: GET /api/users/:id/profile endpoint
→ Scope: Single endpoint, returns user profile JSON
→ Tech stack: Express.js, TypeScript, PostgreSQL

FASE 2: ANÁLISIS DE REQUISITOS
→ Functional:
  - Accept user ID parameter
  - Query database for user
  - Return profile data (name, email, avatar)
  - Handle authentication
→ Non-functional:
  - Response time < 200ms
  - Rate limiting: 100 req/min
  - Input sanitization
  - SQL injection prevention
→ Risks:
  - Unauthorized access
  - User not found
  - Database connection failure

FASE 3: MICRO-TAREAS

→ Task 1: Route handler setup (40 lines)
  → 3.1: Check skills (none applicable)
  → 3.2: Create route with Express
  → 3.3: Self-review ✓
  → 3.4: Generate tests:
    - test_route_exists
    - test_route_method_get
    - test_route_requires_auth
  → 3.5: Execute → 3 passed
  → 3.6: Coverage 100% ✓

→ Task 2: Authentication middleware (45 lines)
  → 3.1: Check skills (none applicable)
  → 3.2: Implement JWT verification
  → 3.3: Self-review ✓
  → 3.4: Generate tests:
    - test_valid_token
    - test_invalid_token
    - test_expired_token
    - test_missing_token
  → 3.5: Execute → 4 passed
  → 3.6: Coverage 100% ✓

→ Task 3: Database query function (50 lines)
  → 3.1: Check skills (none applicable)
  → 3.2: Implement parameterized query
  → 3.3: Self-review ✓
  → 3.4: Generate tests:
    - test_user_found
    - test_user_not_found
    - test_sql_injection_prevention
    - test_database_error_handling
  → 3.5: Execute → 4 passed
  → 3.6: Coverage 100% ✓

→ Task 4: Response formatting (35 lines)
  → 3.1: Check skills (none applicable)
  → 3.2: Format JSON response
  → 3.3: Self-review ✓
  → 3.4: Generate tests:
    - test_response_format
    - test_sensitive_data_hidden
    - test_error_response_format
  → 3.5: Execute → 3 passed
  → 3.6: Coverage 100% ✓

FASE 4: VALIDACIÓN INTEGRAL
→ Security: ✓ Auth, input validation, SQL injection prevention
→ Tests: 14 passed, 0 failed, coverage 100%
→ Quality: ✓ TypeScript types complete
→ Performance: ✓ Query optimized, indexed
→ Architecture: ✓ Separation of concerns

FASE 5: REFINAMIENTO
→ Not needed

FASE 6: ENTREGA
→ Endpoint implemented with 100% test coverage
→ All security measures in place
→ Production-ready
```

### Example 2: React Component Development

**Task:** "Create a reusable Button component"

**Implementation Flow:**

```
FASE 1: PLANIFICACIÓN
→ Objective: Reusable Button component
→ Scope: Single component, multiple variants
→ Tech: React, TypeScript, Tailwind CSS

FASE 2: ANÁLISIS DE REQUISITOS
→ Functional:
  - Display text/label
  - Handle click events
  - Support variants (primary, secondary, danger)
  - Support sizes (sm, md, lg)
  - Disabled state
→ Non-functional:
  - Accessibility (ARIA labels, keyboard navigation)
  - Loading state
  - Icon support
→ Risks:
  - Missing accessibility
  - Inconsistent styling

FASE 3: MICRO-TAREAS

→ Task 1: Component structure (45 lines)
  → 3.1: Check skills (frontend-design skill applicable)
  → 3.2: Create component with props interface
  → 3.3: Self-review ✓
  → 3.4: Generate tests:
    - test_renders_text
    - test_handles_click
    - test_disabled_state
  → 3.5: Execute → 3 passed
  → 3.6: Coverage 100% ✓

→ Task 2: Variant styling (40 lines)
  → 3.1: Use frontend-design skill
  → 3.2: Implement variant classes
  → 3.3: Self-review ✓
  → 3.4: Generate tests:
    - test_primary_variant
    - test_secondary_variant
    - test_danger_variant
    - test_invalid_variant
  → 3.5: Execute → 4 passed
  → 3.6: Coverage 100% ✓

→ Task 3: Accessibility features (35 lines)
  → 3.1: Check skills (web-design-guidelines applicable)
  → 3.2: Add ARIA attributes, keyboard support
  → 3.3: Self-review ✓
  → 3.4: Generate tests:
    - test_aria_label
    - test_keyboard_navigation
    - test_focus_management
  → 3.5: Execute → 3 passed
  → 3.6: Coverage 100% ✓

FASE 4: VALIDACIÓN INTEGRAL
→ Security: ✓ No XSS vulnerabilities
→ Tests: 10 passed, 0 failed, coverage 100%
→ Quality: ✓ TypeScript types complete
→ Performance: ✓ No unnecessary re-renders
→ Architecture: ✓ Reusable, composable

FASE 5: REFINAMIENTO
→ Not needed

FASE 6: ENTREGA
→ Component implemented with 100% test coverage
→ Fully accessible
→ Production-ready
```

---

## ✨ Best Practices

### 1. Start Small

Don't try to implement everything at once. Break down large features into micro-tasks.

**Bad:**
```
Task: "Build complete authentication system"
```

**Good:**
```
Task 1: "Create login endpoint"
Task 2: "Create registration endpoint"
Task 3: "Implement JWT token generation"
Task 4: "Add password hashing"
...
```

### 2. Test as You Go

Write tests immediately after writing code, not at the end.

**Why:** Catching bugs early is 10x cheaper than catching them later.

### 3. Validate Coverage

Aim for ≥99% coverage, but don't obsess over 100%.

**Acceptable:**
- Error handlers that are hard to trigger
- Unreachable code paths
- Third-party library wrappers

**Not Acceptable:**
- Core business logic
- Security-critical code
- User-facing features

### 4. Document Decisions

When making technical decisions, document why:

```python
# Decision: Use parameterized queries instead of string formatting
# Reason: Prevents SQL injection attacks
# Trade-off: Slightly more verbose, but security-critical
def get_user(user_id: int) -> User:
    query = "SELECT * FROM users WHERE id = %s"
    return db.execute(query, (user_id,))
```

### 5. Review Before Moving On

Don't skip the self-review step. It catches:
- Type errors
- Security issues
- Code duplication
- Readability problems

---

## 🔄 Common Patterns

### Pattern 1: CRUD Operations

For CRUD operations, follow this micro-task structure:

1. **Create:** Validation → Database insert → Error handling → Tests
2. **Read:** Query → Authorization → Formatting → Tests
3. **Update:** Validation → Authorization → Update → Tests
4. **Delete:** Authorization → Delete → Cascade handling → Tests

### Pattern 2: API Integration

For external API integration:

1. **Client setup:** HTTP client → Configuration → Tests
2. **Request building:** Parameters → Headers → Authentication → Tests
3. **Response handling:** Parsing → Error handling → Retries → Tests
4. **Error handling:** Timeouts → Rate limits → Network errors → Tests

### Pattern 3: Data Processing

For data transformation:

1. **Input validation:** Schema → Types → Edge cases → Tests
2. **Transformation:** Logic → Edge cases → Performance → Tests
3. **Output formatting:** Structure → Serialization → Tests
4. **Error handling:** Invalid input → Processing errors → Tests

---

## 🐛 Troubleshooting

### Problem: Tests Take Too Long

**Solution:** Use test doubles (mocks, stubs) for external dependencies:

```python
# Instead of real database calls
@patch('database.get_user')
def test_user_not_found(mock_get_user):
    mock_get_user.return_value = None
    # Test logic
```

### Problem: Can't Reach 99% Coverage

**Solution:** Identify what's not covered:

```bash
# Use coverage tools
pytest --cov=module --cov-report=html
```

Then:
1. Check if uncovered code is necessary
2. If yes, write tests for it
3. If no, remove it

### Problem: Micro-Tasks Too Large

**Solution:** Break down further:

```
Original: "Create user service" (200 lines)
→ Too large!

Better:
  Task 1: "User model" (40 lines)
  Task 2: "User repository" (45 lines)
  Task 3: "User service" (50 lines)
  Task 4: "User validation" (35 lines)
```

### Problem: Tests Fail Intermittently

**Solution:** Make tests deterministic:

- Use fixed dates/times
- Mock random values
- Clean up test data
- Use test database

---

## 📚 Additional Resources

- [Installation Guide](./INSTALLATION.md)
- [Main README](../README.md)
- [Contributing Guide](../CONTRIBUTING.md)

---

**Ready to apply the method?** Start your next task and experience systematic, quality-assured development! 🚀
