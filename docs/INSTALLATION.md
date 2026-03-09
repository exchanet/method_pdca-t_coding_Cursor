# Installation Guide / Guia de Instalacion

The method is **one**, in **8 phases**. The technical specification in English and Spanish is in [METHOD.md](../METHOD.md). There is a single Cursor rule: `METHOD-PDCA-T.md` (or use the adapter from `adapters/cursor.md`).

---

## ENGLISH

### Option 1 — enet CLI (Recommended)

`enet` is the exchanet methods manager. It auto-detects your AI agent and installs the correct adapter.

```bash
# Install enet globally
npm install -g @exchanet/enet

# Install PDCA-T
enet install pdca-t
```

enet will:
1. Detect your AI agent (Cursor, Windsurf, Claude Code, etc.)
2. Copy the correct adapter to the right location
3. Confirm installation with the path used

**Verify installation:**
```bash
enet list
# Should show: pdca-t [installed]
```

---

### Option 2 — enet via GitHub (no npm account needed)

```bash
npm install -g github:exchanet/enet
enet install pdca-t
```

---

### Option 3 — Manual Installation

#### Cursor
```bash
mkdir -p .cursor/rules
cp adapters/cursor.md .cursor/rules/method-pdca-t.md
```
The rule activates automatically via `trigger: always_on`.

#### Windsurf
```bash
cat adapters/windsurf.md >> .windsurfrules
```

#### GitHub Copilot
```bash
mkdir -p .github
cp adapters/copilot.md .github/copilot-instructions.md
```

#### Claude Code
```bash
cp adapters/claudecode.md CLAUDE.md
```

#### Claude.ai
Open `adapters/claudeai.md` and paste into the system prompt or start of conversation.

#### ChatGPT / GPT-4o
Open `adapters/openai.md` and paste into Settings > Custom instructions.

#### Aider
```bash
aider --system-prompt "$(cat adapters/aider.md)"
```

#### Any other agent
Open `adapters/generic.md` and paste into your agent context or system prompt.

---

### Optional: CI/CD Pipeline

```bash
mkdir -p .github/workflows
cp .github/workflows/quality.yml .github/workflows/
```

Required tools (add to requirements.txt):
```
pytest
pytest-cov
pytest-benchmark
mypy
ruff
bandit
```

---

### Optional: Templates

```bash
mkdir -p docs/ADRs
cp templates/adr-template.md docs/ADRs/
cp templates/debt-register.md docs/DEBT.md
cp templates/delivery-report.md docs/
```

---

## ESPANOL

### Opcion 1 — CLI enet (Recomendado)

`enet` es el gestor de metodos de exchanet. Detecta automaticamente tu agente de IA e instala el adapter correcto.

```bash
npm install -g @exchanet/enet
enet install pdca-t
```

enet detecta tu agente, copia el adapter correcto y confirma la ruta utilizada.

**Verificar instalacion:**
```bash
enet list
```

---

### Opcion 2 — enet via GitHub

```bash
npm install -g github:exchanet/enet
enet install pdca-t
```

---

### Opcion 3 — Instalacion Manual

| Agente | Comando |
|--------|---------|
| Cursor | `cp adapters/cursor.md .cursor/rules/method-pdca-t.md` |
| Windsurf | `cat adapters/windsurf.md >> .windsurfrules` |
| GitHub Copilot | `cp adapters/copilot.md .github/copilot-instructions.md` |
| Claude Code | `cp adapters/claudecode.md CLAUDE.md` |
| Claude.ai | Pegar contenido de `adapters/claudeai.md` en system prompt |
| ChatGPT | Pegar contenido de `adapters/openai.md` en instrucciones personalizadas |
| Google Antigravity | `cp adapters/antigravity.md .agent/rules/method-pdca-t.md` |
| Aider | `aider --system-prompt "$(cat adapters/aider.md)"` |
| Otro agente | Pegar `adapters/generic.md` en el contexto del agente |
