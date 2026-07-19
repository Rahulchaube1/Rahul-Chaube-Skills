# Context & Memory Management

This document details memory management strategies for AI agents using **Rahul-Chaube-Skills (RCS)** to maximize context-window efficiency.

---

## 💾 Context-Window Conservation

As conversation history grows, LLM performance, response latency, and instruction-following quality degrade. Managing context window space is critical.

### Memory Optimization Rules:

1. **Surgical File Views**: Never view a file's entire content if you only need to inspect a 20-line method. Use the `StartLine` and `EndLine` arguments of `view_file`.
2. **Compact Command Outputs**: Run commands with parameters that limit verbose output (e.g. `git log -n 5` instead of `git log`).
3. **Avoid Repetitive Searches**: Cache search results mentally. Do not run the same `grep_search` or `list_dir` multiple times in a single session.
4. **Summary Truncation**: When referencing past events, reference the conversation transcript `transcript.jsonl` or summarize findings in a compact paragraph rather than paste pages of conversation logs.

---

## 🗄️ Structured Memory Storage

State should be preserved across agents using file-based storage:

- **Task List (`task.md`)**: A checklist tracking task execution progress.
- **Implementation Plan (`implementation_plan.md`)**: Architectural blueprints and approvals.
- **Walkthrough (`walkthrough.md`)**: Historical records of modifications and testing results.
