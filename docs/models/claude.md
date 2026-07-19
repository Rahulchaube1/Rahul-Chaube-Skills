# Anthropic Claude Integration Guide

This guide details the integration guidelines and configurations for **Anthropic Claude** within the RCS platform.

---

## 🌟 Overview

Optimizing guidelines for Claude 3.5 Sonnet and Claude 3.5 Haiku, focusing on XML tags structures, system prompts, and Chain-of-Thought prompts.

---

## 🎯 Best Practices

- **Prompt Engineering**: Adapt constraints to match model characteristics.
- **JSON Output**: Force structured responses using native schemas where supported.
- **Context Budget**: Clean system histories periodically to conserve context limits.

---

## 🚀 Production Recommendations

- **Parameters**: Select temperatures based on specific task demands (e.g. 0.0 for code/logic, 0.7 for creative content).
- **Latency Tuning**: Set batch queues appropriately to balance throughput and response latency.
