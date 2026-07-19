# Pathway: Intermediate Agent Developer

This pathway covers building interactive agents, ReAct loops, planning nodes, state tracking, and tool integrations.

---

## 📚 Syllabus & Key Concepts

### 1. ReAct (Reason-Action) Loop

Understand the classic agentic loop: **Thought -> Action -> Observation -> Thought...**

- How to write a manual loop in Python that executes model-selected tools.
- Preventing infinite execution loops when tools return errors.

### 2. State & Memory Tracking

- Staging conversation history dynamically.
- Implementing databases (like SQLite or Redis) to save agent state.

### 3. Agent Frameworks (LangGraph, CrewAI)

- Building branching logic graphs.
- Setting up router nodes that guide conversations to specialized agents (e.g. Code Agent vs. Search Agent).

---

## 🛠️ Step-by-Step Exercise

1. **Step 1**: Build a ReAct agent using LangGraph.
2. **Step 2**: Add a search tool and a file-write tool.
3. **Step 3**: Verify that the agent can search for information, write it to a markdown file, and successfully end its turn.
