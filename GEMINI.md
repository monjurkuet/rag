# RAG Systems Exploration Lab

## Project Overview
This repository serves as a workbench for exploring, prototyping, and benchmarking various Retrieval-Augmented Generation (RAG) architectures. The goal is to compare different approaches—from standard vector search to agentic hybrid-graph systems—using tools like LangChain, LangFlow, and others.

## Directory Structure
The project is organized to isolate different experiments while sharing common resources.

```text
/
├── implementations/           # Source code for different RAG approaches
│   ├── hybrid_graph_v1/       # (Current) Postgres + Graph + Vector approach
│   ├── langflow_prototypes/   # Flows and configs for LangFlow
│   └── langchain_experiments/ # Python-native LangChain implementations
├── data/                      # Shared datasets, raw documents, and evaluation sets
├── notebooks/                 # Jupyter notebooks for interactive analysis and prototyping
├── scripts/                   # Shared utility scripts (e.g., global setup, evaluation tools)
├── .env                       # Global environment variables
├── pyproject.toml             # Python dependencies (using 'uv')
└── GEMINI.md                  # Project context and agent instructions
```

## Architectures & Implementations

### 1. Hybrid Graph RAG (v1)
*   **Location**: `implementations/hybrid_graph_v1/`
*   **Type**: Hybrid (Vector + Knowledge Graph)
*   **Stack**: PostgreSQL (`pgvector`, `uuid-ossp`), Google GenAI Embeddings, Python.
*   **Key Features**:
    *   Entity extraction and linking.
    *   Graph traversal (shortest path, PageRank).
    *   PostgreSQL as the unified engine for both relational and vector data.

### 2. (Planned) LangFlow
*   **Location**: `implementations/langflow_prototypes/`
*   **Goal**: visual prototyping of agentic workflows.

### 3. (Planned) LangChain
*   **Location**: `implementations/langchain_experiments/`
*   **Goal**: Programmatic, highly custom chains and retrievers.

## Development Standards
*   **Dependency Management**: Use `uv` for fast package management.
*   **Environment**: Keep sensitive keys in `.env` (do not commit).
*   **Data**: Store raw test data in `data/` and do not commit large files.

## Usage
### Running the Hybrid Graph v1
```bash
cd implementations/hybrid_graph_v1
# Run the loader (ensure .env is configured)
uv run load_sample_data.py
```

## Project Planning
*   **`PLANS.md`**: This file tracks the roadmap, active suggestions, and backlog.
            *   **Agent Responsibility**: Always check this file at the start of a session to understand current goals. Proactively suggest updates (additions, completions, deletions) based on user requests and project progress.
        
        ## Workflow & Resilience Protocols
        
        ### 1. Continuous Synchronization (Power Loss Protection)
        To prevent data loss during abrupt disconnects (power outage, crash), we do not wait for a "shutdown" phase.
        *   **PLANS.md**: The agent must update this file **immediately** after completing any significant task or reaching a decision point.
        *   **Git Commits**: The agent must check `git status` and propose a commit after every successful implementation step or stable state. This ensures a "save point" is always available.
        
        ### 2. Startup / Resume
        Since the agent cannot "auto-start" itself, the user must initiate the context restoration.
        *   **Command**: *"Read GEMINI.md and PLANS.md to restore context."*
        *   **Alias Suggestion**: The user is encouraged to create a shell alias (e.g., `rag-resume`) that sends this prompt automatically if their CLI tool supports it.
        