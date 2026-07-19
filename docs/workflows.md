# Workflows & Task Execution

This document details workflow design patterns for complex software development tasks using **Rahul-Chaube-Skills (RCS)**.

---

## 🗂️ Checklists and Task Tracking (`task.md`)

For any multi-step task, the agent must create and maintain a `task.md` file in the conversation artifacts directory.

### Checklist State Indicators:

- `[ ]` **Unstarted**: Task is defined but no work has begun.
- `[/]` **In Progress**: Work is actively being performed on this item.
- `[x]` **Completed**: Task is finished and verified.

---

## 🔀 Workflow Routing

When executing tasks:

1. **Linear Workflows**: Follow steps sequentially (dependencies first). Do not skip steps or try to work on Step 3 before Step 2 is fully verified.
2. **Branching Workflows**: If a step requires an architectural choice, stop and document the choices in `implementation_plan.md`. Wait for the user to review the plan and approve the branch.
3. **Rollbacks**: If a branch fails (e.g. library dependency issue, performance failure), revert commits surgically, update `task.md` with the new plan, and proceed down the alternative branch.
