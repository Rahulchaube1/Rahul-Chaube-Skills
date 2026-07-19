# Llama Integration Guide

This guide details the integration guidelines and configurations for **Llama** within the RCS platform.

---

## 🌟 Overview

Guidelines for Llama 3 and Llama 3.1 open-weights models, focusing on format alignment and context cleaning.

---

## 🎯 Best Practices

- **Prompt Engineering**: Adapt constraints to match model characteristics.
- **JSON Output**: Force structured responses using native schemas where supported.
- **Context Budget**: Clean system histories periodically to conserve context limits.

---

## 🚀 Production Recommendations

- **Parameters**: Select temperatures based on specific task demands (e.g. 0.0 for code/logic, 0.7 for creative content).
- **Latency Tuning**: Set batch queues appropriately to balance throughput and response latency.
