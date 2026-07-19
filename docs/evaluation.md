# Evaluation & Verification

This guide outlines verification and evaluation processes within **Rahul-Chaube-Skills (RCS)**.

---

## 🧪 Goal-Driven Verification Loops

Every code change must be verified against predefined success criteria before the turn is completed.

### Verification Matrix:

| Verification Type | Method                                                       | Scope                                                                 |
| ----------------- | ------------------------------------------------------------ | --------------------------------------------------------------------- |
| **Syntactic**     | Compiler / Linter (e.g. `tsc`, `eslint`, `markdownlint`)     | Checks syntax errors, typos, and formatting alignment.                |
| **Functional**    | Unit Tests / Integration Tests (e.g. `jest`, `pytest`)       | Checks code logic against expected input/output behaviors.            |
| **Systemic**      | End-to-End Tests / API manual tests (`curl`, browser clicks) | Verifies that endpoints and workflows operate in production contexts. |

---

## 🔄 The Verification Loop

```mermaid
graph TD
    CodeEdit[1. Write Surgical Changes] --> RunChecks[2. Run Compiler / Lints]
    RunChecks -- Compile Error --> FixAST[3. Fix AST / Syntax]
    FixAST --> RunChecks
    RunChecks -- Compile Pass --> RunTests[4. Run Unit Tests]
    RunTests -- Test Fail --> FixLogic[5. Refactor Code Logic]
    FixLogic --> RunChecks
    RunTests -- Test Pass --> ManualVerify[6. Run E2E / Manual Curl Check]
    ManualVerify -- Failure --> FixLogic
    ManualVerify -- Success --> Complete[7. Done: Update Walkthrough]
```
