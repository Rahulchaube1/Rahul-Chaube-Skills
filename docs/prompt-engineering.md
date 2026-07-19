# Prompt Engineering

This document details the prompt engineering methodologies implemented within **Rahul-Chaube-Skills (RCS)** to enforce behavioral alignment on LLMs.

---

## 🛠️ Systemic Instruction Patterns

RCS leverages three primary prompt design patterns:

### 1. The Pre-Flight Checklist (Planning Constraint)

Before the model emits any code, we force the generation of a mental model.

- **Instruction Pattern**:
  ```markdown
  Before you make changes or execute any terminal command, write down:

  1. Assumptions: What are you assuming about the data/API?
  2. Confusion: What is ambiguous?
  3. Tradeoffs: What are 2-3 alternative approaches?
  ```

### 2. Negative Constraints (Behavioral Guardrails)

Negative constraints (telling the model what _not_ to do) are often more effective at preventing LLM regressions than positive suggestions.

- **Examples**:
  - "Do NOT write speculative helper functions."
  - "Do NOT alter formatting in lines adjacent to your changes."
  - "Do NOT delete pre-existing comments."

### 3. Verification Loop Triggers (Success Boundaries)

We force the model to define its own test cases before starting, preventing it from halting prematurely.

- **Instruction Pattern**:
  ```markdown
  State your verification plan before editing:

  - Unit Test command: [command]
  - Expected Output: [output]
  - Manual verification curl: [command]
  ```

---

## 🔄 Optimizing for System Prompts

When configuring your own agent templates:

1. **Place constraints at the bottom**: LLMs tend to pay more attention to instructions placed at the beginning and the end of the prompt context (recency bias). Place behavioral guardrails near the final user prompt.
2. **Use Markdown tags**: Use clear enclosures like `<guidelines>` or `<rules>` to help the model separate system guidelines from user inputs.
