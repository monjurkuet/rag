# Project Plans & Roadmap

This document tracks future ideas, planned experiments, and maintenance tasks for the RAG Exploration Lab. It is a living document and should be updated as the project evolves.

## 🚀 Active Suggestions

### Infrastructure & Tooling
- [ ] **LangFlow Setup**: Create a `docker-compose.yml` in `implementations/langflow_prototypes/` to easily spin up a local LangFlow instance.
- [ ] **Unified Data Ingestion**: Create a script to ingest documents from the `data/` directory. This script should be flexible enough to feed different backends (Postgres, Chroma, Pinecone, etc.) to ensure consistent testing data across implementations.

### Experiments
- [ ] **Baseline RAG (LangChain)**: Implement a simple "Standard RAG" (Chunking + Vector Search) in `implementations/langchain_experiments/` to serve as a baseline for performance comparison against the Hybrid Graph approach.
- [ ] **Evaluation Framework**: Design a set of standard questions/queries to run against all implementations to objectively measure quality (e.g., using Ragas or DeepEval).

## ✅ Completed
- [x] **Project Structure**: Organized repository into modular `implementations/`, `data/`, and `scripts/` directories.
- [x] **Security Fix**: scrubbed `.env` from git history using `git-filter-repo`.
- [x] **Documentation**: Added `README.md` and `LICENSE`.
- [x] **Context System**: Established `GEMINI.md` and `PLANS.md` protocol for session persistence.

### Maintenance
- [ ] **Refine Hybrid Graph**: Review the `hybrid_graph_v1` SQL schema for optimization opportunities as the dataset grows.

## 🧊 Backlog / Ideas
- Explore "Agentic RAG" using LangGraph.
- Test different embedding models (OpenAI vs. Google vs. HuggingFace) using the unified ingestion script.
- Create a simple UI (Streamlit/Chainlit) to chat with the different implementations side-by-side.
