# Changelog

All notable changes to the **Simurgh** multi-agent system will be documented in this file.

## [2.0.0] - 2026-01-09

### 🚀 Major Release: The "Memory & Structure" Update

Version 2.0.0 introduces a comprehensive overhaul of the agent architecture, establishing a strict "Source of Truth" via XML workflows and enabling long-term persistence through the new Memory System.

### 🆚 V1 vs V2 Comparison

| Feature | **V1.0.0 (Legacy)** | **V2.0.0 (Current)** |
| :--- | :--- | :--- |
| **Agent Logic** | Scattered across CLI configs | **Centralized** in `.agent/workflows/*.md` (XML) |
| **Consistency** | Gemini/Claude often drifted | **Synchronized** (XML -> TOML/MD) |
| **Persistence** | None (Amnesic sessions) | **Memory System** (`*save`/`*load`) |
| **Scope** | Ambiguous (Some coding) | **Strict Consultancy** (Specs/Plans only) |
| **Orchestrator** | Routing only | **Routing + Help + Context** |
| **Storage** | Root or random folders | **Structured**: `docs/consultancy/{project_id}/` |

### ✨ New Features

-   **Memory System (Global)**: All 6 agents can now `*save` their session state to JSON and `*load` it later to resume work.
    -   Schema includes: `session_summary`, `key_decisions`, `next_steps`, and `artifacts`.
-   **XML Source of Truth**: Agent behaviors are now defined once in `.agent/workflows/` and propagated to all CLI platforms.
-   **Orchestrator Help**: Added `[0] Help & Guidance` (`*help`) to the Orchestrator for interactive tutorials and validiation.
-   **Agent Registry**: A centralized `simurgh/agents/registry.md` now acts as the capabilities catalog.

### 🛠️ Changes

-   **Folder Structure**:
    -   Added `simurgh/agents/{agent}/memory/` for state tables.
    -   Standardized workflow paths to `simurgh/agents/{agent}/workflows/`.
-   **CLI Configuration**:
    -   Gemini `.toml` files are now strictly generated from the XML source.
    -   Claude `.md` files are now strictly generated from the XML source.
-   **Documentation**:
    -   Updated `AGENTS.md` to be an operational manual.
    -   Updated `CLAUDE.md` and `GEMINI.md` with "Key Features".

### ⚠️ Deprecated / Removed

-   **Ad-Hoc Coding**: Agents no longer attempt to write implementation code (e.g., Python/JS files) directly. They purely output consultancy artifacts.
-   **Legacy Configs**: Removed standalone/divergent configuration files that did not match the `.agent` XML definitions.
-   **Git Awareness**: Removed direct Git operation commands from agent personas; agents now rely on the user for version control.

### 🔮 Under Development (What's Next)

-   **Advanced Tool Calling**: Enabling agents to use more sophisticated tools beyond file I/O.
-   **Agent Builder Service**: A meta-agent to help you design and spawn new custom agents.
-   **Workflow Builder Service**: Visual or conversational tool to define complex agent workflows.
-   **MCP Integration**: Native support for Model Context Protocol to connect with external tools.
-   **RAG & CAG Memory**: Implementing Retrieval-Augmented Generation (RAG) and Content-Augmented Generation (CAG) for handling complex, large-scale project memories.
-   **A2A Protocol**: Enabling A2A Protocol for long-running autonomous tasks.
