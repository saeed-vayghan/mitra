# Mitra Agents: Operational Manual

> **For AI Agents:** This document is your primary directive when working within this repository. Follow these protocols strictly.

## 🦅 The Roster

| Agent | Role | Focus | ID |
| :--- | :--- | :--- | :--- |
| **Mitra** | Orchestrator | Guidance, Routing | `mitra-orchestrator` |
| **Zal** | Manager | Planning, Sprints | `mitra-manager` |
| **Sina** | Analyst | Requirements | `mitra-analyst` |
| **Jamshid** | Architect | Systems & Data | `mitra-architect` |
| **Mani** | Designer | UI/UX | `mitra-designer` |
| **Kaveh** | Engineer | Tech Specs | `mitra-engineer` |

## 📂 Repository Layout

- **`.agent/workflows/`**: [SOURCE OF TRUTH] The master XML definitions for all agents. **Edit these first.**
- **`.claude/commands/`**: Claude CLI interfaces. *Must mirror the Source of Truth.*
- **`.gemini/commands/`**: Gemini CLI interfaces. *Must mirror the Source of Truth.*
- **`mitra/`**: Core system directory. See [`mitra/TREE.md`](file:///Users/saeed/Projects/repos/personal/project-mitra/mitra/TREE.md) for full architecture.
- **`mitra/agents/{agent}/`**: Agent-specific support files (persona, workflows).
- **`artifacts/{project_id}/{agent}/memory/`**: The designated folder for session persistence.
- **`artifacts/`**: The strictly designated output folder for all agent artifacts.

## 🛠️ Development Workflow

### 1. Modifying an Agent
When adding a capability or fixing a bug in an agent's logic:
1.  **Edit XML**: Modify `.agent/workflows/mitra-{agent}.md`.
    *   *Rule*: Update the `<menu>` and `<menu-handlers>` sections together.
2.  **Sync Gemini**: Copy updates to `.gemini/commands/mitra/persona/{agent}.toml`.
    *   *Note*: Ensure the TOML variable `prompt = '''...'''` wraps the XML correctly.
3.  **Sync Claude**: Copy updates to `.claude/commands/mitra/{agent}.md`.
4.  **Update Registry**: Reflect changes in `mitra/agents/registry.md`.

### 2. Creating a New Workflow
1.  **Create**: New file in `mitra/agents/{agent}/workflows/{workflow_name}.md`.
2.  **Header**: Include a YAML frontmatter with `description` and `version`.
3.  **Body**: Define the step-by-step process for the agent to follow.
4.  **Link**: Add a handler in the Agent's XML to load this workflow.

## 🧠 Memory System Protocols

**Global Capability**: All agents support `*save` and `*load`.

-   **State Path**: `artifacts/{project_id}/{agent}/memory/state-{version}-{topic}-{yyyy-mm-dd}.json`
-   **Schema**:
    ```json
    {
      "timestamp": "ISO-8601",
      "context": { "topic": "...", "summary": "..." },
      "artifacts": [ { "type": "PRD", "path": "artifacts/..." } ]
    }
    ```
-   **Rule**: Never modify the `memory-manager.md` logic without testing the JSON read/write cycle.

## [!IMPORTANT] **MANDATORY MEMORY PROTOCOL**
When a user asks to "save state", "persist context", or "remember this", you **MUST** execute the `memory-manager` workflow defined in your `.toml` or `.agent` file.
- **DO NOT** create ad-hoc markdown files like `MEMORY.md`.
- **DO NOT** summarize in chat only.
*Failure to follow this protocol breaks the 'Time Travel' capability of the system.*

## Constraints & Laws

1.  **Unified Context**: All agents must read `config.yaml` to respect `project_id`.
2.  **Output Isolation**: All artifacts must go to `artifacts/{project_id}/`.
