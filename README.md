# 🤖 Multi-Agent AI Content Generation Studio (LangGraph + Ollama)

A production-grade, local-first compound AI engineering system that acts as an automated content production team. The application leverages **LangGraph** for advanced multi-agent state orchestration, **LangChain** for robust interface parsing, and a local **Ollama** engine for completely cost-free semantic composition. 

It features real-time search grounding and an automated dual-layer image fail-safe pipeline that bypasses API rate limits gracefully.

---

## 🏗️ Core Architecture (Orchestrator-Workers Map-Reduce)

This system implements an asynchronous Map-Reduce architecture optimized to maximize local computation output while keeping model token windows narrow and fast:

1. **Router Node:** Analyzes the topic matrix and classifies the configuration constraint parameters (`closed_book`, `hybrid`, or `open_book`).
2. **Research Node:** Performs deep web grounding via the **Tavily API** to gather structural citations and real-time facts.
3. **Orchestrator Node:** Generates clean, production-scoped task outline configurations using strict schema validation parameters.
4. **Worker Nodes (Parallel Fan-out):** In parallel, separate worker nodes compose distinct chapters natively in technical Markdown.
5. **Reducer Subgraph:** Integrates paragraph objects, executes placeholder injections (`[[IMAGE_1]]`), and calls the asset canvas to apply illustrations.

---

## ✨ Key Features
- **100% Free Text Compilation:** Powered entirely by a local **`qwen2.5-coder:7b`** model running on Ollama, saving thousands of dollars in cloud API tokens.
- **Strict Structural Enforcement:** Uses deterministic `json_schema` parsing modes to ensure a local 7B model maps complex, multi-level Pydantic data schemas cleanly without crashing.
- **Adaptive Sidebar Layout Toggles:** Includes an explicit **📄 Generate GitHub README Mode** sidebar switch. When active, it re-routes the internal prompts to build repository README structures rather than technical articles.
- **Robust API Fail-safe Handling:** Catches cloud image generation `429 RESOURCE_EXHAUSTED` limitations silently. If throttled, it immediately falls back to contextual, high-signal Unsplash layouts so image asset components are never broken.

---

## 🛠️ Installation & Setup

### 1. Prerequisites
Ensure you have Python 3.10+ and [Ollama](https://ollama.com/) installed locally.

### 2. Initialize the Local Engine
Pull and boot up the optimized coding model inside your system command prompt:
```bash
ollama run qwen2.5-coder:7b
