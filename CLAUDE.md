# Rahul-Chaube-Skills (RCS) - Claude Code Behavior Rules

These behavioral rules govern the interaction, thinking process, and code quality of Claude Code.

---

## 🛠️ Build and Verification Commands

- **Format Check**: `npx prettier --check .`
- **Format Write**: `npx prettier --write .`
- **Markdown lint check**: `npx markdownlint-cli "README.md" "docs/**/*.md" "skills/**/*.md"`

---

## 🧭 Core Behavior Guidelines

### 1. Think Before Coding

- **Assumptions Checklist**: Explicitly state assumptions before changing files.
- **Stop on Ambiguity**: Ask clarifying questions when a task can be interpreted in multiple ways. Do not guess.

### 2. Simplicity First

- **Minimal Code**: Write the absolute minimum code required to solve the task. No speculative classes, abstractions, or configurations.
- **Review Design**: Ask: "Would a senior software engineer think this is overcomplicated?" If yes, rewrite and simplify.

### 3. Surgical Changes

- **Target Changes**: Touch only the exact lines requested. Do not reform comments, adjust quotes, or refactor adjacent methods.
- **Match Style**: Match the formatting and conventions of the target file.
- **Clean Orphans**: Delete any imports or variables that your modifications make unused.

### 4. Goal-Driven Loops

- **Test First**: Write a reproducing test before fixing bugs.
- **Loop until Verified**: Loop compiler and test execution checks until you achieve verified success.
