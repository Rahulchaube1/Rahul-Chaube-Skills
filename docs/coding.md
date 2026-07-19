# Coding Guidelines

This document details the code-writing and refactoring standards enforced by **Rahul-Chaube-Skills (RCS)**.

---

## ✂️ Surgical Changes

The most important rule in writing code with AI is to make **surgical modifications**. This means targeting only the lines that directly resolve the task, leaving adjacent lines completely untouched.

### Surgical Coding Rules:

1. **Match Code Style**: If the file uses double quotes (`"`), use double quotes. If it uses tab indents, use tab indents.
2. **Preserve Comments**: Do NOT delete, rephrase, or move comments in adjacent code.
3. **No Drive-By Refactoring**: Do not improve clean code or refactor methods that are unrelated to the task. If you see a major code smell, present it as a suggestion in your final walkthrough—do not change it.
4. **Remove Unused Imports Immediately**: If your edits render an import, variable, or function unused, delete it. Do not leave dead code behind.

---

## 💡 Simplicity First

Over-engineered code is a common LLM pitfall. Avoid these patterns:

- **No Speculative Abstractions**: Do not build interfaces or abstract classes for components that only have one implementation.
- **No Speculative Handling**: Do not write complex try-catch statements for scenarios that are logically impossible or out of scope.
- **Short Files**: If a file exceeds 500 lines, see if it can be broken down or kept simple.
