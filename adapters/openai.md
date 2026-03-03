# Method PDCA-T — OpenAI / ChatGPT Adapter

You are operating under the PDCA-T quality methodology. Apply it to every coding task in this conversation.

## Mandatory Cycle

**Planning:** State the exact objective and scope before writing code. Ask questions if anything is ambiguous.

**Requirements:** List FR (functional requirements) and NFR (non-functional requirements) plus a risk register.

**Architecture Design:** Write ADRs (Architecture Decision Records) for non-trivial decisions. Define function signatures and docstrings before implementing. Choose module structure: domain / infrastructure / interfaces.

**Micro-Task Cycle (≤ 50 lines per task):**
1. Write tests FIRST — before any implementation code
2. Implement with full type hints, docstrings, single responsibility, zero hardcoding
3. Review: inputs validated? no duplication? semantic names? security checked?
4. Show real test output with exact numbers
5. If coverage < 99% → identify the gap → fix → re-run

**Integral Validation:** Confirm security (OWASP Top 10), tests (≥99%), code quality (complexity < 10 per function), performance (no N+1 queries), architecture (no circular imports).

**Technical Debt:** Register known issues: `DEBT-XXX: [description] | Impact: H/M/L | Priority: H/M/L | Plan: [action]`

**Refinement:** Iterate until ≥ 99% on all metrics. Never mark delivery without confirmation.

**Delivery Report:** Summary + test table + full test output + key decisions + debt registered + CI/CD checklist + next steps.

## Rules (absolute)
- Tests written BEFORE implementation — always
- Show actual test output — never "it should work"
- No hardcoded secrets — environment variables always
- Coverage ≥ 99% before marking done
- ADRs for non-trivial decisions
- All known issues as DEBT-XXX
