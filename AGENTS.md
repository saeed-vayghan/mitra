# Simurgh Agents

The **Simurgh** system consists of specialized AI agents working together as a collective intelligence.


## 🦅 The Roster

See the [Agent Registry](simurgh/agents/registry.md) for a full list of available agents and their capabilities.


## 📂 Project Structure
```bash
project-root/
├── .gemini/                 # Gemini CLI Configurations
│   └── commands/            # Command definitions
│       └── simurgh/
│           └── persona/
│               └── {agent}.toml
├── .agent/                  # Antigravity IDE Configurations
│   └── workflows/           # IDE Workflows
├── .claude/                 # Claude Code Configurations
├── simurgh/                 # Agent Core Logic
│   └── agents/
│       └── {agent_role}/    # e.g., engineer, architect
│           ├── persona.md   # Identity & Capabilities
│           ├── workflows/   # Executable processes
│           │   ├── registry.md
│           │   └── {workflow}.md
│           └── assets/      # Reference knowledge
│               ├── {category}/
│               │   └── {asset}.md
│               └── registry.md
└── docs/
    └── consultancy/         # ALL Agent Outputs & Memories
        └── {YYYYMMDD}-{ProjectName}/
            ├── design.md
            ├── specs.md
            └── session_summaries.md
```
## ⚙️ Configuration

- **.gemini/**: Contains configurations for the **Gemini CLI** (Command definitions, personas, settings).
- **.agent/**: Contains configurations for the **Antigravity IDE** (Workflows, IDE-specific settings).
- **.claude/**: Contains configurations for the **Claude Code** (Custom commands).

> [!WARNING]
> **Synchronization Rule**: If you modify an agent's capability or persona in one folder (e.g., `.gemini`), you **MUST** update the equivalent files in the other folders (`.agent` and `.claude`) to keep the system behavior consistent.


## 📚 Documentation

For detailed capabilities, usage guides, and configuration, please refer to the **[Agent Registry](simurgh/agents/registry.md)**.


## 🚀 Interaction

You can interact with agents individually or collectively:

- **Individual**: `/simurgh:persona:<name>` (e.g., `/simurgh:persona:engineer`)
- **Collective**: `/simurgh:orchestrator` (Starts a session with the Orchestrator/Host)
