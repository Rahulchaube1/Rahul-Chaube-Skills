# Frequently Asked Questions (FAQ)

Here are answers to the most common questions about **Rahul-Chaube-Skills (RCS)**.

---

## General Questions

### What is Rahul-Chaube-Skills (RCS)?

RCS is a highly comprehensive, modular library of AI agent and LLM guidelines, prompting frameworks, and specialized skill instruction sets. It helps prevent common coding agent errors, guides critical thinking, and teaches models to follow surgical, simple, and goal-driven execution loops.

### How does this differ from the original Karpathy guidelines?

The original guidelines were derived from a single social media post, covering a few basic guidelines (Think Before Coding, Simplicity First, Surgical Changes, Goal-Driven Execution) in a single file.
RCS takes these foundational concepts and expands them into a fully structured, multi-dimensional project containing:

- 45 specialized skill guides (ranging from systems engineering, RAG, vector databases to deep reasoning, startups, and specific LLM optimization guidelines).
- Comprehensive documentation detailing philosophy, agent loops, context-window memory management, and evaluation.
- SVG diagrams explaining architectural flow.
- Native integration files for Cursor, Claude Code, Windsurf, and custom agent runtimes.

---

## Integration and Usage

### Can I use RCS with Cursor?

Yes! RCS provides pre-packaged rules under `.cursor/rules/`. When you open a project with these files, Cursor's Composer and Agent modes will read and enforce these instructions automatically.

### Can I use RCS with Claude Code?

Yes! You can append our `CLAUDE.md` to your workspace root. Claude Code will automatically ingest these guidelines at the start of any conversation.

### How do I use individual skills?

Each skill folder (e.g. `skills/ai-ml/rag/SKILL.md`) contains a description and instructions. When building an agent workflow or prompting an LLM:

1. Provide the content of the `SKILL.md` file as a system prompt or part of the agent's instructions.
2. In agent frameworks (like LangGraph, CrewAI, or autogen), you can read these markdown files dynamically and insert them into specific agent node contexts.

---

## Troubleshooting

### The model is spending too much time thinking. How do I fix this?

Ensure you are using the correct rules. Read our guidance on [AI Agents](docs/ai-agents.md) and [Philosophy](docs/philosophy.md). You can add a constraint telling the model: "For simple typo fixes or obvious code additions, bypass the deep thinking planning phases and execute surgically."

### Can I customize the skills?

Absolutely. RCS is built to be customized. You can copy the skill folders you need into your project and customize the `SKILL.md` instructions to match your team's specific styles, standards, and libraries.
