# 🧪 RAG Exploration Lab

A comprehensive workbench for prototyping, benchmarking, and exploring various Retrieval-Augmented Generation (RAG) architectures. This repository serves as a testing ground for comparing different approaches—from standard vector search to advanced Agentic Hybrid-Graph systems.

## 🚀 Overview

The goal of this project is to implement and evaluate different RAG strategies side-by-side using a unified dataset and evaluation framework.

**Current Implementations:**
*   **Hybrid Graph RAG (v1)**: A custom implementation leveraging **PostgreSQL** as a unified engine for both Vector Search (`pgvector`) and Knowledge Graph traversal.
    *   *Features*: Entity extraction, PageRank-style node importance, Shortest path retrieval.

**Planned Modules:**
*   **LangFlow**: Visual prototyping for agentic workflows.
*   **LangChain**: Python-native chains for baseline comparisons.
*   **Agentic RAG**: Investigating LangGraph for multi-agent orchestration.

## 📂 Project Structure

The repository is organized to support modular experiments:

```text
/
├── implementations/           # Source code for different RAG engines
│   ├── hybrid_graph_v1/       # Postgres + Graph + Vector implementation
│   ├── langflow_prototypes/   # Visual flow definitions (Planned)
│   └── langchain_experiments/ # Standard RAG baselines (Planned)
├── data/                      # Shared raw documents and evaluation datasets
├── notebooks/                 # Jupyter notebooks for interactive analysis
├── scripts/                   # Shared utilities (ingestion, eval metrics)
└── GEMINI.md                  # Context file for AI Agents
```

## 🛠️ Setup & Installation

### Prerequisites
*   **Python 3.12+**
*   **[uv](https://github.com/astral-sh/uv)** (Fast Python package manager)
*   **PostgreSQL 14+** (with extensions: `vector`, `pg_trgm`, `uuid-ossp`)

### Quick Start

1.  **Clone the repository**
    ```bash
    git clone https://github.com/monjurkuet/rag.git
    cd rag
    ```

2.  **Install Dependencies**
    ```bash
    uv sync
    ```

3.  **Configure Environment**
    Copy the example configuration and add your API keys (Google GenAI, Database credentials).
    ```bash
    cp .env.example .env
    ```

4.  **Initialize Database (Hybrid Graph v1)**
    ```bash
    psql -U <your_db_user> -d <your_db_name> -f implementations/hybrid_graph_v1/schema.sql
    ```

## 📖 Usage

### Running the Hybrid Graph Loader
To seed the database with sample data and test the embedding generation:

```bash
cd implementations/hybrid_graph_v1
uv run load_sample_data.py
```

## 🗺️ Roadmap

See [PLANS.md](./PLANS.md) for the detailed project roadmap, active tasks, and backlog.

## 🤝 Contributing

This is an experimental lab. Feel free to open issues or submit PRs with new RAG architectures or datasets!

## 📄 License

MIT License. See [LICENSE](./LICENSE) for details.
