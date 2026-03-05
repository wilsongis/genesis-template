# 🧬 Project Genesis: [Project Name]

## 🤖 ATTENTION: AI AGENT ONBOARDING
**Read this before performing any tasks.** You are operating as the **Legacy Mentor**. This repository is governed by the **Agent Memory Protocol (v1.0)**.

### 1. Your Single Source of Truth
All project state, architectural decisions, and session memory are stored in **`AGENTS.md`**. 
- **Requirement:** At the start of every session, you must read `AGENTS.md`.
- **Requirement:** Before concluding, you must update `AGENTS.md` with the new project state.

### 2. The Command Bridge (Universal)
Do not use raw shell commands. Use `just` to ensure cross-platform (Mac/Windows) stability.

| Task | Command | AI Tooling Note |
| :--- | :--- | :--- |
| **Initialize** | `just init` | Sets up venv and template files. |
| **Research Sync** | `just research-sync` | Ingests `/docs/research` into NotebookLM. |
| **Research Auth** | `just research-auth` | Logs into AntiGravity/NotebookLM MCP. |
| **Start Server** | `just start` | Manages Podman container lifecycle. |
| **Native Run** | `just run` | Runs FastAPI via `uv` (Native). |
| **Standards** | `just lint` | Enforces Ruff formatting. |

### 3. Research-First Protocol
This is a research-heavy project. You are prohibited from writing feature code unless it is grounded in the documents found in `/docs/research/` or the linked **NotebookLM**.
- **Step 1:** Use `notebooklm-mcp` to query the project's knowledge base.
- **Step 2:** Cross-reference with `AGENTS.md` constraints.
- **Step 3:** Propose implementation.

### 4. Container Environment
The environment is containerized via `Containerfile`. 
- **Tech Stack:** FastAPI, PostGIS, Python 3.12 (UV managed).
- **Access:** The server runs on port `8000`.
- **Database:** PostGIS spatial extensions are pre-configured.

### 5. Memory Recovery
If you lose context or the user says **"Status"**, execute:
1. `cat AGENTS.md`
2. `ls docs/research`
3. Summarize the next steps from the `## Active Context` section of `AGENTS.md`.

---
**Legacy Standard Enforced.**
"Take a deep breath and work on this problem step by step."

## How to Use the Template
Once it is set as a template, anyone (including yourself or any AI assistants) can create a new project based on this exact structure.

There are two ways to use it:

1. Through the UI: Go to the GitHub repository and click the green Use this template button, then select Create a new repository.
2. Through the CLI: You can use the GitHub CLI to clone it directly:

```bash
gh repo create <new-repo-name> --template wilsongis/genesis-template
```