# Simurgh Agents: Operational Manual

> **For AI Agents:** This document is your primary directive when working within the `project-specy-party` repository. Follow these protocols strictly.

## 🦅 The Roster

| Agent | Role | Focus | ID |
| :--- | :--- | :--- | :--- |
| **Simurgh** | Orchestrator | Guidance, Routing | `simurgh-orchestrator` |
| **Zal** | Manager | Planning, Sprints | `simurgh-manager` |
| **Sina** | Analyst | Requirements | `simurgh-analyst` |
| **Jamshid** | Architect | Systems & Data | `simurgh-architect` |
| **Mani** | Designer | UI/UX | `simurgh-designer` |
| **Kaveh** | Engineer | Tech Specs | `simurgh-engineer` |

## 📂 Repository Layout

- **`.agent/workflows/`**: [SOURCE OF TRUTH] The master XML definitions for all agents. **Edit these first.**
- **`.gemini/commands/`**: Gemini CLI interfaces. *Must mirror the Source of Truth.*
- **`.claude/commands/`**: Claude CLI interfaces. *Must mirror the Source of Truth.*
- **`simurgh/agents/`**: Support file storage (personas, registry, memory).
- **`docs/consultancy/`**: The strictly designated output folder for all agent artifacts.

## 🛠️ Development Workflow

### 1. Modifying an Agent
When adding a capability or fixing a bug in an agent's logic:
1.  **Edit XML**: Modify `.agent/workflows/simurgh-{agent}.md`.
    *   *Rule*: Update the `<menu>` and `<menu-handlers>` sections together.
2.  **Sync Gemini**: Copy updates to `.gemini/commands/simurgh/persona/{agent}.toml`.
    *   *Note*: Ensure the TOML variable `prompt = '''...'''` wraps the XML correctly.
3.  **Sync Claude**: Copy updates to `.claude/commands/simurgh/{agent}.md`.
4.  **Update Registry**: Reflect changes in `simurgh/agents/registry.md`.

### 2. Creating a New Workflow
1.  **Create**: New file in `simurgh/agents/{agent}/workflows/{workflow_name}.md`.
2.  **Header**: Include a YAML frontmatter with `description` and `version`.
3.  **Body**: Define the step-by-step process for the agent to follow.
4.  **Link**: Add a handler in the Agent's XML to load this workflow.

## 🧠 Memory System Protocols

**Global Capability**: All agents support `*save` and `*load`.

-   **State Path**: `simurgh/agents/{agent}/memory/state-{yyyy-mm-dd}-{topic}.json`
-   **Schema**:
    ```json
    {
      "timestamp": "ISO-8601",
      "context": { "topic": "...", "summary": "..." },
      "artifacts": [ { "type": "PRD", "path": "docs/consultancy/..." } ]
    }
    ```
-   **Rule**: Never modify the `memory-manager.md` logic without testing the JSON read/write cycle.

## ✅ Verification Checklist

Before confirming a task is complete, ensure:

- [ ] **XML Validity**: No broken tags in `.agent` files.
- [ ] **Sync Check**: Do `.gemini` and `.claude` match the `.agent` XML?
- [ ] **Directory Exists**: Did you create the `memory/` or `workflows/` folder if it was new?
- [ ] **Consultancy Rule**: Did you ensure NO implementation code was generated for the target app?
- [ ] **Registry**: Is the new feature listed in `simurgh/agents/registry.md`?

## ⛔ Constraints & Laws

1.  **Consultants Only**: Agents produce specs, plans, and docs. They do NOT write app code (e.g., `src/index.js`).
2.  **Unified Context**: All agents must read `config.yaml` to respect `project_id`.
3.  **Output Isolation**: All artifacts must go to `docs/consultancy/{project_id}/`.
