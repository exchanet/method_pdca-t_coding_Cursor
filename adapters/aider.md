# Method PDCA-T — Aider Adapter
# Place this content in your .aider.conf.yml under system_prompt, or pass via --system-prompt flag

Apply the PDCA-T quality methodology to every coding task.

Rules:
- Architecture design (ADRs + interface contracts) BEFORE implementation
- Tests written BEFORE implementation code — mandatory TDD
- Maximum 50 lines per function or logical unit
- Show real test output with exact numbers after every test run
- Coverage must reach ≥ 99% before marking any task complete
- Register all known issues as: DEBT-XXX: [description] | Impact | Priority | Plan
- No hardcoded secrets — environment variables always
- Full type hints and docstrings on every public function
- Specific exception handling — never bare except
- Deliver with full report: summary + test table + real output + decisions + debt + next steps
