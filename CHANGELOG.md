# Changelog

Format based on Keep a Changelog (https://keepachangelog.com/en/1.0.0/).

---

## [Unreleased]

### Removed
- Spanish rule file (`.cursor/rules/METODO-PDCA-T.md`) and Spanish skill (`.cursor/skills/metodo-pdca-t/`) to avoid duplication and conflict. The method is now a single rule in English (`METHOD-PDCA-T.md`) and a single skill (`method-pdca-t`).

### Changed
- Documentation updated to present the method as **8 phases** with a **bilingual** technical specification in METHOD.md (EN + ES). READMEs and INSTALLATION guides now reference only METHOD-PDCA-T.md and method-pdca-t; METHOD.md is the canonical spec for both languages.

---

## [3.0.0] - 2025-03

### Added
- Phase 3: Architecture Design (ADRs + interface contracts before implementation)
- Phase 6: Technical Debt Management (DEBT-XXX format with priority system)
- Multi-agent adapters: Windsurf, Claude Code, Claude.ai, ChatGPT/GPT-4o, Aider, Generic
- enet CLI installation: enet install pdca-t
- GitHub Actions CI/CD pipeline with coverage gate, mypy, ruff, bandit
- Bilingual templates: delivery-report.md, adr-template.md, debt-register.md
- Full METHOD.md technical reference (EN + ES)
- docs/INSTALLATION.md and docs/USAGE.md
- CONTRIBUTING.md with contribution guidelines
- examples/tax-calculator/ full worked example
- examples/rest-api/ REST API example

### Changed
- Total phases: 6 -> 8
- TDD now explicitly mandatory (tests BEFORE code, enforced in all adapters)
- Test categories expanded: happy path + error + edge + security + performance
- Delivery report template expanded with CI/CD checklist and debt table
- README fully bilingual with adapter installation table
- Coverage threshold enforcement moved to CI pipeline (--cov-fail-under=99)

### Fixed
- Cursor adapter now uses correct trigger: always_on frontmatter
- Phase 4 sub-cycle explicit about showing REAL output (not hypothetical)

---

## [2.0.0] - 2024-12

### Added
- Spanish README (README_ES.md)
- Basic CI/CD guidance
- Delivery report template (basic version)

### Changed
- Phases reorganized for clarity
- Self-review checklist expanded

---

## [1.0.0] - 2024-09

### Added
- Initial release: 6-phase PDCA-T method
- Cursor adapter (.cursor/rules/METHOD-PDCA-T.md)
- ~~Spanish Cursor adapter (METODO-PDCA-T.md)~~ (removed in Unreleased; single rule only)
- README in English and Spanish
- Example: tax calculator
