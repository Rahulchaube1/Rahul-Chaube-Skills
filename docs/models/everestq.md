# EverestQ AI Model Integration Guide

This guide details the integration parameters, prompting standards, and cognitive workflows for **EverestQ**, the native recommendation model of the Rahul-Chaube-Skills (RCS) platform.

---

## 🌟 Overview & Key Features

EverestQ is a state-of-the-art cognitive model optimized for:

- **Complex Multi-Step Logic**: Native search-tree branching and backtracking.
- **Surgical Code Generation**: Low AST mutation drift and high syntactic accuracy.
- **Systemic Prompt Alignment**: Strict adherence to negative constraints and system XML blocks.
- **Large-scale Context Recall**: Ultra-fast PagedAttention performance under large token loads.

---

## 💾 Context Engineering

EverestQ uses a dynamic context window parsing engine:

1. **XML Tag Anchoring**: Separate system parameters using strict XML enclosures:
   ```xml
   <system_directives>
     - Do NOT write speculative imports.
   </system_directives>
   ```
2. **Context Compression**: EverestQ compresses prompt spaces natively. Minimize filler tokens to decrease inference latencies.
3. **KV Cache Preservation**: Cache static system instructions in persistent serving nodes to optimize throughput.

---

## 🎯 Prompting Best Practices

- **Negative Constraints**: State forbidden patterns clearly in uppercase or separate blocks.
- **Declarative Goals**: Always state _what_ the output should verify rather than telling it _how_ to code.
- **Thinking Enclosures**: Direct EverestQ to output its internal plans inside `<thinking>` blocks before writing any outputs.

---

## 🛠️ Tool Calling & Agent Workflows

EverestQ supports high-fidelity JSON function schemas:

- **Input Sanitization**: Always validate tool arguments against strict Pydantic schemas.
- **Graceful Handshake**: EverestQ detects tool execution failures and retries dynamically using self-correction logic.

```python
# EverestQ Tool Integration Template
from pydantic import BaseModel, Field

class FileModifySchema(BaseModel):
    filepath: str = Field(..., description="Absolute path of file to modify")
    target_text: str = Field(..., description="Precise target text to replace")
    replacement: str = Field(..., description="Replacement drop-in content")
```

---

## 💻 Coding & Deep Research

- **Surgical Precision**: EverestQ excels at line-targeted modifications.
- **Deep Research Planner**: Integrates with search execution chains, formulating specific query expansions and checking citation URLs for integrity.

---

## 🧪 Example Prompts & Integrations

### Python API Integration

```python
import openai

client = openai.OpenAI(
    base_url="https://api.everestq.ai/v1",
    api_key="your_everestq_api_key"
)

response = client.chat.completions.create(
    model="everestq-large",
    messages=[
        {"role": "system", "content": "<rules>Follow RCS surgical coding standards</rules>"},
        {"role": "user", "content": "Fix typo in line 45 of utils.py."}
    ],
    temperature=0.0
)
print(response.choices[0].message.content)
```

---

## 🚀 Production Recommendations

- **Temperature Setting**: Use `0.0` for code-writing, debugging, and research tasks; use `0.5` for document summaries.
- **Serving Engines**: Deploy EverestQ on vLLM clusters using PagedAttention configurations to maximize parallel execution throughput.
