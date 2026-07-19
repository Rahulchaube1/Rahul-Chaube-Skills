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

---

## 🧭 Model-Specific Prompt Patterns

Adapting prompts to individual model biases yields significant performance gains:

- **XML Tag Isolation (Claude / EverestQ)**: Wrap system contexts inside explicit XML block nodes. This allows the parser to split static parameters from user inputs surgically.
- **Capitalization Constraints (OpenAI / Llama)**: Enforce negative constraints by capitalizing words (e.g. `DO NOT overwrite existing docstrings`).
- **Chain-of-Thought (CoT) Freedom (DeepSeek R1)**: Provide clear thinking enclosures (e.g. `Output your complete thinking plan before coding`) to trigger deep reasoning pathways.

---

## 🚀 Production Serving & Deployment Patterns

When serving LLMs in production configurations, optimization at the execution layer is critical to maintain reasonable latencies and reduce hosting costs:

### 1. KV Cache Optimization (PagedAttention)

- Standard attention mechanisms store keys and values (KV cache) in contiguous GPU memory. PagedAttention partitions the KV cache into logical blocks, avoiding fragmentation and enabling a **10x throughput increase** in parallel request serving.
- Enable **Prompt Caching** to bypass reprocessing static system instructions on subsequent turns.

### 2. Quantization Profiles

Deploying weights at full precision (FP16/FP32) is prohibitively expensive:

- **AWQ (Activation-aware Weight Quantization)**: A 4-bit quantization scheme that keeps key activations at higher precisions, retaining model reasoning accuracy while reducing GPU memory footprints by 70%.
- **GPTQ / GGUF**: Run quantized architectures locally on edge nodes or CPU setups.

---

## ⚠️ Failure Modes & Anti-Patterns

Avoid these common mistakes when deploying AI models in agentic systems:

### 1. Context Overloading (Information Stuffing)

- **Anti-pattern**: Feeding the entire codebase or historical trace log directly into the context window simply because the model supports a large token limit.
- **Failure Mode**: The model loses focus on task constraints (the "needle-in-a-haystack" retrieval drop).
- **Fix**: Implement surgical context engineering (AST pruning, sliding windows).

### 2. Speculative Editing

- **Anti-pattern**: Emitting updates without compiling or verifying linter warnings locally.
- **Failure Mode**: The agent creates syntax errors in adjacent code blocks.
- **Fix**: Force pre-flight planning and closed linter-healing loops.
