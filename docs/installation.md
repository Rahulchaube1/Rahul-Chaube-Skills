# Installation & Setup

This guide walks you through integrating **Rahul-Chaube-Skills (RCS)** into your AI development environments.

---

## 🚀 Supported Platforms

RCS is a platform-agnostic specification. It can be integrated as:

1. **Cursor MDC Rules** (Highly recommended for Editor integration)
2. **Claude Code Behavioral Rules**
3. **Windsurf System Guidelines**
4. **Agent SDK System Instructions** (LangGraph, CrewAI, Autogen, etc.)

---

## 1. Cursor Setup (Composer / Agent)

Cursor natively reads custom rulesets defined inside `.cursor/rules/`.

1. Copy the rules from this repository:
   ```bash
   mkdir -p .cursor/rules/
   cp -r path-to-rcs/.cursor/rules/* .cursor/rules/
   ```
2. The rulesets (`rcs-behavior-guidelines.mdc`, `rcs-coding.mdc`, etc.) will automatically apply to all composer prompts and actions.

---

## 2. Claude Code Setup

Claude Code looks at a `CLAUDE.md` file in the root of your project directory for guidance on formatting, tests, and behavior.

1. Copy the `CLAUDE.md` file to the root of your workspace:
   ```bash
   cp path-to-rcs/CLAUDE.md ./CLAUDE.md
   ```
2. Claude Code will read this file during start-up.

---

## 3. Custom AI Agent Integration (Python / Node.js)

To load RCS skills dynamically into custom workflows:

### Python Example (LangGraph / CrewAI)

```python
import os

def load_rcs_skill(category: str, skill_name: str) -> str:
    """Loads a specific RCS skill instructions string."""
    skill_path = os.path.join("skills", category, skill_name, "SKILL.md")
    if not os.path.exists(skill_path):
        raise FileNotFoundError(f"Skill not found: {skill_path}")

    with open(skill_path, "r", encoding="utf-8") as f:
        content = f.read()

    # Optional: strip YAML frontmatter
    if content.startswith("---"):
        parts = content.split("---", 2)
        if len(parts) >= 3:
            return parts[2].strip()
    return content.strip()

# Load reasoning skill for your Agent Node
reasoning_prompt = load_rcs_skill("core-behaviors", "reasoning")
```
