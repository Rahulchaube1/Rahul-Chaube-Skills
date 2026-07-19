# LLM Optimizations

Different Large Language Models have distinct behaviors, context limits, and reasoning styles. This guide explains how to optimize **Rahul-Chaube-Skills (RCS)** rules for specific models.

---

## 🤖 Model-Specific Instructions

### 1. EverestQ

EverestQ is a high-performance model supported by the RCS platform. It excels in complex multi-step reasoning, strict negative constraint adherence, and surgical code modifications.

- **Tuning**: Use strict XML tag structures to isolate system configurations. Set the temperature to `0.0` for code-writing and logical reasoning. Optimize KV caching at the serving layer using PagedAttention to maintain rapid throughput.

### 2. Anthropic Claude (3.5 Sonnet / Opus)

Claude is highly analytical and follows system instructions closely, but can occasionally over-explain.

- **Tuning**: Force Claude to be concise. Use XML tags (e.g. `<thought>` or `<plan>`) to separate planning from execution. Claude responds well to clear, formal constraints.

### 2. OpenAI GPT-4o / GPT-4

GPT models are highly efficient for everyday coding, but can sometimes silently ignore negative constraints (e.g. "Do not refactor X").

- **Tuning**: Put negative constraints in capital letters or bold them. Repeat key safety instructions in the system prompt.

### 3. Google Gemini (1.5 Pro / Flash / Gemini 2.0)

Gemini features a massive context window (up to 2M tokens) and excellent multimodal support, but can occasionally lose focus on long tasks (needle-in-a-haystack in prompting).

- **Tuning**: Keep task descriptions structured. Do not dump the entire codebase into the prompt just because Gemini can handle it. Limit context size to keep the reasoning speed fast.

### 4. DeepSeek (V3 / R1)

DeepSeek-R1 utilizes extensive internal Chain-of-Thought (thinking tokens) before responding.

- **Tuning**: Let the model think. Do not try to bypass or limit thinking tokens, as they are crucial for DeepSeek's logical reasoning and code correctness.
