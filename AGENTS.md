# Simurgh Agents System

The **Simurgh** system consists of specialized AI agents working together as a collective intelligence. This document outlines the system architecture, file structure, and core capabilities.

## 🦅 The Roster

| Agent | Role | Focus |
| :--- | :--- | :--- |
| **Simurgh** | Orchestrator | Guidance, Routing, Party Host |
| **Zal** | Manager | Planning, Sprints, Task Dispatch |
| **Sina** | Analyst | Requirements, Research, Strategy |
| **Jamshid** | Architect | Backend, Frontend, Cloud Systems |
| **Mani** | Designer | UI, UX, Design Systems |
| **Kaveh** | Engineer | Technical Specs, Security, Docs |

See the [Agent Registry](simurgh/agents/registry.md) for detailed capabilities.

---

## 🏗️ System Architecture

### 1. Source of Truth (XML)
The definitive logic for every agent is defined in **XML-wrapped Markdown** files within `.agent/workflows/`.
- **Location**: `.agent/workflows/simurgh-{agent}.md`
- **Content**: Persona, Menu Options, Handlers, System Instructions, and Embedded Resources.

### 2. CLI Synchronization
The XML definitions are synchronized to CLI-specific configurations to ensure consistent behavior across platforms:
- **Gemini**: `.gemini/commands/simurgh/persona/{agent}.toml`
- **Claude**: `.claude/commands/simurgh/{agent}.md`

> [!IMPORTANT]
> **Edit Rule**: Always edit the **XML** files in `.agent/workflows/` first. Then sync changes to `.gemini` and `.claude`.

---

## 🧠 Memory System (New)

All agents now possess **Long-Term Memory** to persist session context.

### Capabilities
- **`*save`**: Saves the current session state, including:
    - Project context (`project_id`, `user_name`)
    - Session Summary & Key Decisions
    - Links to created Artifacts (PRDs, Specs, etc.)
    - Next Steps
- **`*load`**: Lists saved sessions and restores variables to resume work exactly where you left off.

### Storage
State files are stored as JSON in: `simurgh/agents/{agent}/memory/state-{yyyy-mm-dd}-{topic}.json`.

---

## 📂 Project Structure

```bash
project-root/
├── .agent/workflows/          # [SOURCE OF TRUTH] Agent XML Definitions
├── .gemini/                   # Gemini CLI Configuration (Synced)
├── .claude/                   # Claude CLI Configuration (Synced)
├── simurgh/                   # Core Logic & Resources
│   └── agents/
│       ├── registry.md        # Central Capabilities List
│       └── {agent}/           # e.g., analyst, architect
│           ├── persona.md     # Narrative Identity
│           ├── workflows/     # Task-specific Logic (e.g., prd.md, memory-manager.md)
│           └── memory/        # [NEW] JSON State Files
└── docs/
    └── consultancy/           # Output Directory
        └── {project_id}/      # All generated docs go here
            ├── 2026-01-09-PRD.md
            └── design-system.md
```

## 📜 Consultancy Policy

**Simurgh Agents are Consultants, not Coders.**
- **Output**: Specifications, Plans, Diagrams, Reports, and Analysis.
- **Restriction**: Agents do NOT write implementation code (no production Python/JS/etc.).
- **Goal**: To provide the highest level of strategic and architectural guidance for the Human Developer to implement.

## 🚀 Interaction

### 1. Orchestrator (Hub)
Start here if you need guidance or want to collaborate with multiple agents.
```bash
/simurgh:orchestrator
```
*Menu includes: `*party` (Multi-agent), `*help` (Tutorial), and direct calls to other agents.*

### 2. Direct Access
Call specific specialists directly:
- `/simurgh:persona:manager` (Zal)
- `/simurgh:persona:architect` (Jamshid)
- `/simurgh:persona:analyst` (Sina)
- `/simurgh:persona:engineer` (Kaveh)
- `/simurgh:persona:designer` (Mani)
