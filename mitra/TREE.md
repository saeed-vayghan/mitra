# Mitra Directory Architecture

This document defines the definitive directory structure for the Mitra multi-agent Full-Lifecycle Development Platform. AI agents MUST reference this tree to locate their personas, workflows, and memory states.

## 🏁 Project Root Structure

```text
/
├── .agent/workflows/       Mirror of manifests formatted for AntiGravity Desktop.
├── .claude/commands/       Mirror of manifests formatted for Claude.
├── .gemini/commands/       Mirror of manifests formatted for Gemini.
├── artifacts/       Strictly designated output folder for all agent artifacts.
│   └── {project_id}/       Project-specific output (e.g., upgrade-agents).
│       └── {agent_id}/     Agent-specific project outputs.
│           └── memory/     JSON files containing rich session state (*save/*load).
└── mitra/
    ├── config.yaml         Global configuration (project_id, user_name).
    ├── TREE.md             [THIS FILE] The definitive structure guide.
    └── agents/             Configuration and data for specialized agents.
        ├── registry.md     Master list of agent capacities and triggers.
        └── {agent_id}/     Agent-specific directory (e.g., analyst, manager).
            ├── persona.md  Markdown fragment defining the agent's identity.
            └── workflows/  Markdown files defining specialized multi-step tasks.
```

## 🧠 Memory Protocol

-   **Path**: `{project-root}/artifacts/{project_id}/{agent_id}/memory/`
-   **Filename Pattern**: `agent-{agent_id}-state-{version}-{yyyy-mm-dd}.json`

## 🛠️ Workflow Protocol

-   **Path**: `{project-root}/mitra/agents/{agent_id}/workflows/`
-   **Execution**: Workflows are loaded dynamically by the `workflow-loader` skill.
