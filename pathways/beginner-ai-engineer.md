# Pathway: Beginner AI Engineer

This pathway introduces you to prompt design, APIs, structured outputs, and basic model configurations.

---

## 📚 Syllabus & Key Concepts

### 1. Prompt Anatomy & System Rules

Learn how to structure a prompt so that the LLM behaves predictably:

- **System Prompts**: Enforce global constraints (e.g. "Do not write explanations").
- **User Prompt**: The direct task query.
- **Enclosures**: Use XML tags to isolate variables (e.g. `<code_to_fix>{{code}}</code_to_fix>`).

### 2. JSON Schema & Structured Outputs

Ensure the model returns raw JSON data instead of text paragraphs.

- Using OpenAI's `response_format: {"type": "json_object"}`.
- Writing Pydantic schemas to validate outputs in Python.

### 3. Model APIs and Tool Definitions

- Making your first client requests to OpenAI, Anthropic, or local model endpoints.
- Defining a basic JSON tool schema to let the model request math calculations or file readings.

---

## 🛠️ Step-by-Step Exercise

1. **Step 1**: Write a Python script to request a structured translation from an LLM.
2. **Step 2**: Use Pydantic to validate that the output contains `translated_text` and `confidence_score`.
3. **Step 3**: Handle validation errors gracefully.
