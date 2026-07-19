# Contributing to Rahul-Chaube-Skills (RCS)

Thank you for your interest in contributing to **Rahul-Chaube-Skills (RCS)**! This repository aims to provide the most comprehensive, production-ready, and advanced skills library for LLMs, AI agents, and autonomous systems.

We welcome contributions of new skills, improvements to existing documentation, bug fixes in guidelines, and new workflow architectures.

---

## Code of Conduct

By participating in this project, you agree to abide by our [Code of Conduct](CODE_OF_CONDUCT.md). Please report any unacceptable behavior to `security@rahulchaube.com`.

---

## How Can I Contribute?

### 1. Proposing a New Skill

If you have a skill that is not currently represented:

1. Open an issue using the **Skill Proposal Template**.
2. Discuss the target use-case, key principles, and prompt engineering instructions with the maintainers.
3. Once approved, create a pull request placing your skill under `skills/<category>/<skill-name>/SKILL.md`.

### 2. Improving Existing Skills

AI models evolve rapidly. If you find a skill has:

- Outdated prompts or instructions
- Edge cases where the model fails to follow instructions
- Missing model-specific instructions (e.g. Claude Code or Cursor details)

Please submit a Pull Request with surgical edits to the corresponding `SKILL.md` or markdown document.

### 3. Fixing Bugs or Guidelines

If there are errors in our markdown syntax, broken links, or spelling mistakes, feel free to open a quick PR.

---

## Style Guidelines

To keep the library structured and clean, please adhere to the following rules:

### Directory Structure

All skills must be categorized under one of the major directories inside `skills/`:

- `core-behaviors/`
- `engineering/`
- `ai-ml/`
- `models/`
- `business-product/`

Each skill directory must contain a `SKILL.md` file.

### SKILL.md Format

Each skill file must start with a YAML frontmatter:

```yaml
---
name: skill-name-slug
description: Clear, action-oriented description of what this skill does.
---
```

Ensure the markdown follows a logical heading hierarchy (`#`, `##`, `###`), and uses callouts or code snippets appropriately.

### Language and Tone

- Write in **clear, concise, and professional English**.
- Use imperative, action-oriented instructions for prompt guidelines (e.g., "State your assumptions explicitly" instead of "It is good if you write down the assumptions").
- Avoid speculative features or complex language.

---

## Pull Request Process

1. Fork the repository and create your branch from `main`.
2. Implement your changes surgically (touch only what you must).
3. Format your markdown files with `npx prettier --write .`.
4. Ensure linting passes using `npx markdownlint-cli "README.md" "docs/**/*.md" "skills/**/*.md"`.
5. Submit your PR and describe the changes and motivations clearly in the template.
