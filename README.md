# Langgraph-Learning-Modules-CampusX

This repository documents my hands-on learning and experimentation with **LangGraph**, following the **CampusX LangGraph playlist**.

Each module demonstrates a core workflow pattern supported by LangGraph, implemented using Jupyter notebooks for clarity and step-by-step exploration.

---

## Repository Structure

```
Langgraph-Learning-Modules-CampusX
├── 1_sequential_flow
├── 2_parallel_flow
├── 3_conditional_flow
├── 4_iterative_flow
├── 5_basic_chatbot
├── 6_persistence
├── 7_langsmith
├── 8_tools
├── 9_Human_in_the_loop
├── 10_subgraphs
├── 11_memory
├── LICENSE
├── requirements.txt
└── README.md
```

---

## Workflow Modules

### 1. Sequential Flow

- **Concepts covered:**
  - Sequential node execution
  - State passing across nodes
  - Prompt chaining

- **Notebooks:**
  - `1_bmi_calculator.ipynb` – Simple deterministic computation pipeline
  - `2_simple_llm.ipynb` – Single-step LLM invocation
  - `3_prompt_chaining.ipynb` – Multi-step prompt chaining using LangGraph

### 2. Parallel Flow

- **Concepts covered:**
  - Parallel node execution
  - Shared state aggregation
  - Independent evaluation paths

- **Notebooks:**
  - `1_batsman_workflow.ipynb` – Parallel analysis of a batsman’s performance
  - `2_upsc_evaluator.ipynb` – Parallel evaluation of UPSC-style answers

### 3. Conditional Flow

- **Concepts covered:**
  - Conditional edges
  - Decision-based routing
  - State-driven control flow

- **Notebooks:**
  - `1_quadratic_solver.ipynb` – Route logic based on discriminant value
  - `2_review_handling.ipynb` – Sentiment-based review handling workflow

### 4. Iterative Flow

- **Concepts covered:**
  - Iterative execution
  - Loop control using state
  - Termination conditions

- **Notebooks:**
  - `post_generator.ipynb` – Iterative content generation workflow

### 5. Basic Chatbot

- **Concepts covered:**
  - Minimal chat graph
  - Message state handling

- **Notebooks:**
  - `chatbot.ipynb`

### 6. Persistence

- **Concepts covered:**
  - Checkpointing
  - Fault tolerance
  - State recovery

- **Notebooks:**
  - `1_joke_explain.ipynb`
  - `2_fault_tolerance.ipynb`

### 7. LangSmith

- **Concepts covered:**
  - Custom tracing
  - Observability and debugging

- **Notebooks:**
  - `custom_trace.ipynb`

### 8. Tools

- **Concepts covered:**
  - Tool calling
  - MCP
  - RAG workflows

- **Contents:**
  - `1_tools.ipynb`
  - `2_mcp.py`
  - `3_rag.ipynb`
  - `intro-to-ml.pdf`

### 9. Human-in-the-Loop (HITL)

- **Concepts covered:**
  - Human approval loops
  - Interruptions and resumes

- **Files:**
  - `1_basic.ipynb`
  - `2.1_stock_purchase_without_hitl.py`
  - `2.2_stock_purchase_with_hitl.py`

### 10. Subgraphs

- **Concepts covered:**
  - Modular graph composition
  - Separate vs shared state

- **Notebooks:**
  - `1_separate_state.ipynb`
  - `2_shared_state.ipynb`

### 11. Memory

Covers **in-context** and **out-of-context** memory using LangGraph and Postgres.

#### 11.1 In-Context Memory

- **Concepts covered:**
  - Persistence with Postgres
  - Trimming
  - Deletion
  - Summarization

- **Notebooks:**
  - `1_persistence_with_postgres.ipynb`
  - `2_trimming.ipynb`
  - `3_deletion.ipynb`
  - `4_summarization.ipynb`

#### 11.2 Out-of-Context Memory

- **Concepts covered:**
  - Long-term memory concepts
  - External storage
  - Postgres-backed memory

- **Notebooks:**
  - `1_memories_basics.ipynb`
  - `2_chatbot_implementation.ipynb`
  - `3_postgres.ipynb`

---

## Setup

### 1. Dependencies:

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

### 2. Environment Variables:

Create a .env file in the project root:

```.env
GOOGLE_API_KEY=
LANGSMITH_TRACING=true
LANGSMITH_ENDPOINT=https://api.smith.langchain.com
LANGSMITH_API_KEY=
LANGSMITH_PROJECT=langgraph-learning-modules-campusX
```

Alternatively, rename `.env.example` to `.env` and update the value accordingly.

### 3. For Folder 11_memory:

```bash
cd 11_memory/
docker compose up -d
```

Cleanup:

```bash
docker ps
docker stop 11_memory-postgres-1   # replace if name differs
docker rm 11_memory-postgres-1

docker images | grep postgres
docker rmi postgres:16
docker rmi -f postgres:16          # if image is still in use
```

---

## License

This project is licensed under the MIT License.
