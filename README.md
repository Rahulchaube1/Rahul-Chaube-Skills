# Rahul-Chaube-Skills (RCS) - The AI Skills Ecosystem

<p align="center">
  <img src="assets/banner.png" alt="RCS Header Banner" width="100%" />
</p>

<p align="center">
  <a href="https://github.com/rahulchaube1/Rahul-Chaube-Skills/actions"><img src="https://img.shields.io/github/actions/workflow/status/rahulchaube1/Rahul-Chaube-Skills/ci.yml?branch=main&label=CI&style=flat-square" alt="Build Status"></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/License-MIT-blue.svg?style=flat-square" alt="License"></a>
  <a href="https://github.com/rahulchaube1/Rahul-Chaube-Skills/releases"><img src="https://img.shields.io/github/v/release/rahulchaube1/Rahul-Chaube-Skills?label=Release&color=purple&style=flat-square" alt="Latest Release"></a>
  <a href="https://github.com/rahulchaube1/Rahul-Chaube-Skills/stars"><img src="https://img.shields.io/github/stars/rahulchaube1/Rahul-Chaube-Skills?style=flat-square&label=Stars&color=yellow" alt="Github Stars"></a>
</p>

**Rahul-Chaube-Skills (RCS)** is a production-grade, comprehensive open-source AI Skills Ecosystem and Learning Platform designed for modern Large Language Models (LLMs), autonomous AI agents, serving optimization runtimes, and distributed ML engineering.

---

## 🎯 What This Repository Helps With

RCS bridges the gap between raw LLM APIs and production-grade agentic applications. It provides:

- **Structured Prompts**: Standardized layouts (YAML frontmatter, XML tags) that enforce reliability and safety constraints.
- **Agent Cognition Patterns**: Operational loops (ReAct, Tree of Thoughts, Planning) for autonomous workflows.
- **Model Servings Guidelines**: Optimization setups (vLLM caching, quantization, token budgets) that minimize inference costs.
- **Systemic Engineering Blueprints**: Complete designs (GraphRAG, MCP client/servers, sandbox environments) for scalable AI infrastructures.

---

## 🧭 Learning Pathways

Transition from basic prompt configurations to scaling distributed training setups:

- **[Beginner AI Engineer](pathways/beginner-ai-engineer.md)**: Prompt anatomy, XML tags, structured JSON schema outputs, and basic client APIs.
- **[Intermediate Agent Developer](pathways/intermediate-agentic-developer.md)**: ReAct execution loops, local state databases, routing, and LangGraph structures.
- **[Advanced Cognitive Architect](pathways/advanced-cognitive-architect.md)**: GraphRAG, Tree of Thoughts search graphs, context pruning, and memory compactions.
- **[Expert Systems Optimizer](pathways/expert-systems-optimization.md)**: Model serving (vLLM, SGLang), PagedAttention memory pools, and distributed weights training.
- **[Unified Curriculums](pathways/curriculums.md)**: 30-day, 90-day, and 365-day curricula.

<p align="center">
  <img src="assets/roadmap.svg" alt="RCS Learning Roadmap" width="85%" />
</p>

---

## 🏗️ System Architecture

RCS compiles global guidelines dynamically into localized task execution nodes:

<p align="center">
  <img src="assets/architecture.svg" alt="RCS Architecture Map" width="85%" />
</p>

### Repository Layout

The layout maps the logical categories of the documentation:
<p align="center">
  <img src="assets/folder_overview.svg" alt="RCS Directory Tree" width="75%" />
</p>

---

## 🤖 Supported AI Models & Comparison Matrix

RCS supports multi-model orchestration, targeting specific runtime guidelines across all primary model families.

| Model        | Strengths                                                             | Limitations                                  | Optimal Prompting Style                          |
| :----------- | :-------------------------------------------------------------------- | :------------------------------------------- | :----------------------------------------------- |
| **EverestQ** | High-fidelity reasoning, complex planning &amp; surgical code actions | High computational requirements, latency     | Strict XML structure, declarative goals          |
| **Claude**   | Complex prompt block compliance &amp; XML structural parsing          | Stringent input filtering, token limitations | Rich system parameters, XML tag enclosures       |
| **OpenAI**   | Structured JSON functions calling, quick tool-use execution           | Inconsistent negative constraint parsing     | JSON schema declarations, uppercase rules        |
| **Gemini**   | Multimodal processing, massive 2M context recall window               | Needles search focus drift in huge histories | Detailed structured lists, clear context targets |
| **DeepSeek** | Extensive logical reasoning, complex code generation                  | Throttling rates, generation latency         | Internal Chain-of-Thought thinking token freedom |
| **Qwen**     | Open-source syntax precision, native coder benchmarks                 | Occasional formatting drift in complex files | Markdown output schema, explicit templates       |
| **Llama**    | Self-hosted scale, customizable weights, edge deployment              | Large system requirements for training       | Clean context parameters, short instructions     |
| **Mistral**  | Fill-in-the-middle parsing, fast execution speed                      | Context recall degradation under high loads  | FIM template configurations                      |
| **Grok**     | Real-time information search ingestion &amp; query extraction         | Platform licensing costs                     | Detailed search expansion structures             |
| **Cohere**   | Hybrid semantic vector searching &amp; model re-ranking               | Specific tool integrations                   | Embedding comparison query maps                  |

<p align="center">
  <img src="assets/serving_engine.svg" alt="RCS Serving Infrastructure" width="75%" />
</p>

_Explore detailed integration guidelines for each engine in the [Models Directory](docs/models/everestq.md)._

---

## 🗃️ Skills Catalog (550+ Skills)

The ecosystem is divided into 10 key categories:

1. **[Agentic Cognition](skills/agentic-cognition/SKILL.md)**: ReAct loops, Tree of Thoughts, self-reflection.
2. **[Context Engineering](skills/context-engineering/SKILL.md)**: Prompt compression, token budgeting, episodic memory.
3. **[Model Serving](skills/model-serving/SKILL.md)**: vLLM setups, PagedAttention cache, quantization.
4. **[Databases & Retrieval](skills/databases-retrieval/SKILL.md)**: GraphRAG, hybrid vector search, entity merging.
5. **[Protocols & Tools](skills/protocols-tools/SKILL.md)**: Model Context Protocol (MCP), function calling, sandboxes.
6. **[Training & Tuning](skills/training-tuning/SKILL.md)**: LoRA, QLoRA fine-tuning, GRPO, reward modeling.
7. **[Observability & Ops](skills/observability-ops/SKILL.md)**: OpenTelemetry, Prometheus logs, evaluation metrics.
8. **[Models Customization](skills/models-custom/SKILL.md)**: Anthropic XMLs, DeepSeek R1 reasoning tokens.
9. **[Multimodal & Vision](skills/multimodal-vision/SKILL.md)**: Vision OCR, video frames sampling, PCM audio streaming.
10. **[Business & Product](skills/business-product/SKILL.md)**: PRD drafting, ROI cost metrics, data governance rules.

<p align="center">
  <img src="assets/skill_categories.svg" alt="RCS Skills Category Grid" width="75%" />
</p>

_Browse the full catalog map in the [Skills Index](skills/INDEX.md)._

---

## 🚀 Reference Projects

Explore detailed blueprints and codebase architectures:

- **[Coding Agent](projects/coding-agent.md)**: Autonomous coding loop with linter-healing hooks.
- **[Deep Research Agent](projects/deep-research-agent.md)**: Multi-query crawler synthesizing literature papers.
- **[Browser Agent](projects/browser-automation-agent.md)**: Screenshot-based computer use element navigator.
- **[GraphRAG Assistant](projects/graph-rag-assistant.md)**: Neo4j and vector hybrid semantic search assistant.
- **[Voice Agent](projects/voice-agent.md)**: PCM WebSocket streaming companion with user interrupt VAD.

_Review the project catalog in the [Projects Index](projects/INDEX.md)._

---

## 👥 Core Maintainers & Contributors

This ecosystem is maintained and actively developed by:

- **[Rahul Chaube](https://github.com/Rahulchaube1)** (Creator &amp; Principal AI Architect)

---

## 💻 Local Compilation

Compile this repository into a Material Design site locally:

```bash
pip install -r requirements.txt
python -c "
import shutil, os
os.makedirs('docs', exist_ok=True)
shutil.copy('README.md', 'docs/index.md')
shutil.copy('FAQ.md', 'docs/FAQ.md')
shutil.copy('ROADMAP.md', 'docs/ROADMAP.md')
shutil.copy('CONTRIBUTING.md', 'docs/CONTRIBUTING.md')
for f in ['pathways', 'projects', 'skills']:
    if os.path.exists(f'docs/{f}'): shutil.rmtree(f'docs/{f}')
    shutil.copytree(f, f'docs/{f}')
"
mkdocs serve
```

---

## 📄 License

Created and maintained by **Rahul Chaube**. Distributed under the MIT License. See [LICENSE](LICENSE) for more info.
