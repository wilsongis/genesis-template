# AGENTS.md: [Project Name]

## 1. Project Identity
**Objective:** [Describe the project's purpose here]
**Status:** Verified

## 2. Research & Grounding
- **Notebook Name:** "Project Genesis Master Research"
- **Notebook ID:** `1a2b3c4d-5e6f-7g8h-your-unique-id-here`
- **MCP Provider:** AntiGravity / notebooklm-mcp
- **Local Source Sync:** `/docs/research/`
- **Primary (Dev):** `just research-sync`
- **Secondary (Prod):** `just notebook=prod research-sync`

**Rule:** Always use the Dev notebook for experimental features. Only sync to Prod when the `SRS` (Software Requirements Specification) is finalized.

## 3. Global Tech Stack (The Standard)
- **Backend:** FastAPI (Python)
- **Frontend:** Jinja2 + HTMX + Tailwind
- **Automation:** Just + UV
- **MCP Tools:** NotebookLM-MCP

## 4. The Agent Memory Protocol
**Read-Execute-Write Memory Protocol:**
1. **READ**: Always read `AGENTS.md` before starting a task to gain context.
2. **EXECUTE**: Work on the objective step-by-step according to the Global Tech Stack.
3. **WRITE**: Update the `AGENTS.md` with current status and new knowledge before ending the task.

## 5. Critical Commands (The Justfile Bridge)

| Command | Action | Platform | Description |
| :--- | :--- | :--- | :--- |
| `just start` | **Container Start** | Universal | Builds if missing and starts the Podman container. |
| `just run` | **Native Start** | Universal | Runs FastAPI via `uv` for rapid development. |
| `just research-sync` | **Sync Knowledge** | Universal | Pushes `/docs/research` to NotebookLM. |
| `just lint` | **Clean Code** | Universal | Runs Ruff for standards enforcement. |

## 5. Active Context & Todo
- [x] Initialize repository from Genesis template
- [ ] Connect NotebookLM ID
- [ ] Define initial SRS (Software Requirements Specification)

---
⏱️ **State:** Verified | 🧠 **Memory:** Fresh | 🛠️ **Platform:** Universal