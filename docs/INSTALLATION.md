# Installation Guide

Complete guide to installing and configuring the PDCA-T Enhanced Coding Method for Cursor AI.

**Author:** Francisco J Bernades  
**GitHub:** [@exchanet](https://github.com/exchanet)

---

## 📋 Prerequisites

Before installing, ensure you have:

- **Cursor IDE** installed and running
- A project directory where you want to apply the method
- Basic familiarity with Cursor's rules system

---

## 🚀 Installation Methods

### Method 1: Install as Cursor Rule (Recommended)

This method activates the PDCA-T method automatically for all tasks in your project.

#### Step 1: Clone or Download the Repository

```bash
git clone https://github.com/exchanet/method_pdca-t_coding_Cursor.git
cd method_pdca-t_coding_Cursor
```

Or download the ZIP file from GitHub and extract it.

#### Step 2: Create `.cursor/rules/` Directory

Navigate to your project directory and create the rules directory if it doesn't exist:

```bash
# On Linux/Mac
mkdir -p /path/to/your/project/.cursor/rules

# On Windows (PowerShell)
New-Item -ItemType Directory -Path ".cursor\rules" -Force
```

#### Step 3: Choose Language Version and Copy the Rule File

**Choose your preferred language:**

**English Version (Recommended for international projects):**
```bash
# On Linux/Mac
cp .cursor/rules/METHOD-PDCA-T.md /path/to/your/project/.cursor/rules/

# On Windows (PowerShell)
Copy-Item ".cursor\rules\METHOD-PDCA-T.md" -Destination ".\path\to\your\project\.cursor\rules\"
```

**Spanish Version:**
```bash
# On Linux/Mac
cp .cursor/rules/METODO-PDCA-T.md /path/to/your/project/.cursor/rules/

# On Windows (PowerShell)
Copy-Item ".cursor\rules\METODO-PDCA-T.md" -Destination ".\path\to\your\project\.cursor\rules\"
```

**Note:** Both versions contain the same methodology. Choose based on your team's language preference. The English version (`METHOD-PDCA-T.md`) is recommended for international projects.

#### Step 4: Verify Installation

The rule file should have this header:

```yaml
---
trigger: always_on
---
```

If `trigger: always_on` is present, Cursor will automatically apply the method to all tasks.

#### Step 5: Test the Installation

1. Open Cursor in your project
2. Start a new coding task
3. The AI should automatically follow the PDCA-T method (you'll see it planning, analyzing requirements, creating micro-tasks, etc.)

---

### Method 2: Install as Reusable Skill

This method allows you to use the PDCA-T method as a skill that can be referenced when needed.

#### Step 1: Clone or Download the Repository

Same as Method 1, Step 1.

#### Step 2: Create `.cursor/skills/` Directory

```bash
# On Linux/Mac
mkdir -p /path/to/your/project/.cursor/skills

# On Windows (PowerShell)
New-Item -ItemType Directory -Path ".cursor\skills" -Force
```

#### Step 3: Choose Language Version and Copy the Skill Directory

**Choose your preferred language:**

**English Version (Recommended for international projects):**
```bash
# On Linux/Mac
cp -r .cursor/skills/method-pdca-t /path/to/your/project/.cursor/skills/

# On Windows (PowerShell)
Copy-Item -Recurse ".cursor\skills\method-pdca-t" -Destination ".\path\to\your\project\.cursor\skills\"
```

**Spanish Version:**
```bash
# On Linux/Mac
cp -r .cursor/skills/metodo-pdca-t /path/to/your/project/.cursor/skills/

# On Windows (PowerShell)
Copy-Item -Recurse ".cursor\skills\metodo-pdca-t" -Destination ".\path\to\your\project\.cursor\skills\"
```

**Note:** Both versions contain the same methodology. Choose based on your team's language preference. The English version (`method-pdca-t`) is recommended for international projects.

#### Step 4: Reference the Skill

When starting a task, you can reference the skill:

**For English version:**
```
Use the method-pdca-t skill for this task
```

**For Spanish version:**
```
Use the metodo-pdca-t skill for this task
```

Or the AI will automatically detect and use it when appropriate.

---

## 🔧 Configuration

### Customizing the Method

### Language Versions

This repository includes two language versions:

- **English:** `.cursor/rules/METHOD-PDCA-T.md` and `.cursor/skills/method-pdca-t/`
  - Recommended for international projects
  - Standard for open-source contributions
  
- **Spanish:** `.cursor/rules/METODO-PDCA-T.md` and `.cursor/skills/metodo-pdca-t/`
  - For Spanish-speaking teams
  - Same methodology, different language

**Choose the version that best fits your team's needs.** Both are functionally identical.

### Customizing the Method

If you want to customize the method for your specific needs:

1. **Edit the rule file** (`.cursor/rules/METHOD-PDCA-T.md` for English or `.cursor/rules/METODO-PDCA-T.md` for Spanish):
   - Modify phase descriptions
   - Adjust coverage thresholds (though ≥99% is recommended)
   - Add project-specific requirements

2. **Create project-specific rules**:
   - Keep the base PDCA-T rule
   - Add additional rules for project-specific patterns

### Disabling Auto-Activation

If you want to use the method manually instead of auto-activation:

1. Open `.cursor/rules/METODO-PDCA-T.md`
2. Change `trigger: always_on` to `trigger: manual` or remove the trigger line
3. Reference the method explicitly when needed

---

## ✅ Verification Checklist

After installation, verify:

- [ ] `.cursor/rules/METHOD-PDCA-T.md` (English) or `.cursor/rules/METODO-PDCA-T.md` (Spanish) exists in your project
- [ ] The file contains `trigger: always_on` in the frontmatter
- [ ] Cursor recognizes the rule (check Cursor's rules panel)
- [ ] Starting a new task triggers the PDCA-T workflow

---

## 🐛 Troubleshooting

### Rule Not Activating

**Problem:** The method doesn't seem to be applied automatically.

**Solutions:**
1. Check that the file is in `.cursor/rules/` (not `.cursor/rule/` or other variations)
2. Verify you're using the correct filename:
   - English: `METHOD-PDCA-T.md`
   - Spanish: `METODO-PDCA-T.md`
3. Verify the YAML frontmatter is correct:
   ```yaml
   ---
   trigger: always_on
   ---
   ```
4. Restart Cursor IDE
5. Check Cursor's rules panel to see if the rule is listed

### Skill Not Found

**Problem:** The AI can't find the skill when referenced.

**Solutions:**
1. Verify the skill is in the correct directory:
   - English: `.cursor/skills/method-pdca-t/SKILL.md`
   - Spanish: `.cursor/skills/metodo-pdca-t/SKILL.md`
2. Check the directory structure matches exactly
3. Try referencing it with the correct name:
   - English: `method-pdca-t/SKILL.md`
   - Spanish: `metodo-pdca-t/SKILL.md`

### Tests Not Running

**Problem:** The method requires tests but pytest isn't configured.

**Solutions:**
1. Install pytest: `pip install pytest` or `npm install --save-dev jest`
2. Configure test framework in your project
3. The method will adapt to your test framework (pytest, jest, unittest, etc.)

---

## 📚 Next Steps

After installation:

1. **Read the Usage Guide:** See [USAGE.md](./USAGE.md) for examples
2. **Review Examples:** Check the `examples/` directory
3. **Start Coding:** Begin your next task and watch the method in action!

---

## 🔄 Updating

To update to the latest version:

```bash
cd method_pdca-t_coding_Cursor
git pull origin main

# Then re-copy the files to your project
cp .cursor/rules/METODO-PDCA-T.md /path/to/your/project/.cursor/rules/
```

---

## 💡 Tips

- **Keep the rule file in version control** - This ensures your team uses the same method
- **Customize for your team** - Add team-specific requirements to the rule
- **Combine with other rules** - The PDCA-T method works well with other Cursor rules
- **Monitor coverage** - Use tools like `pytest-cov` or `jest --coverage` to track coverage

---

## 📞 Support

If you encounter issues:

1. Check the [Troubleshooting](#-troubleshooting) section above
2. Open an issue on GitHub: [https://github.com/exchanet/method_pdca-t_coding_Cursor/issues](https://github.com/exchanet/method_pdca-t_coding_Cursor/issues)
3. Review the [Usage Guide](./USAGE.md) for examples

---

**Ready to code with confidence?** Start your next task and experience the PDCA-T method! 🚀
