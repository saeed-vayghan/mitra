# Changelog

All notable changes to the **Mitra** multi-agent system will be documented in this file.

## [2.2.0] - 2026-04-04

### 🏗️ Standardized Architecture Update

This update finalizes the transition to a centralized, YAML-based memory architecture and enforces strict agent-namespacing for all system outputs.

### ✨ New Features

-   **YAML-Based Persistence**: Migration from JSON to YAML for all session state files, improving readability and tool-compatibility.
-   **Absolute Technical Linking**: All agent workflows now contain absolute `file://` URI links to their respective `memory-manager.md` for consistent navigation across platforms.

### 🛠️ Changes

-   **Agent-Namespaced Artifacts**: Updated all agent personas and 15+ workflows to strictly save files in `{project_root}/artifacts/{project_id}/{agent-id}/`.
-   **Uniform Deliverable Rules**: Implemented a standardized "Deliverables & Storage" footer across all non-memory-manager workflows to ensure protocol compliance.
-   **Memory Manager Synchronization**: All 6 core agent memory managers now use an identical YAML schema and scanning protocol.

---

## [2.1.0] - 2026-04-04

### 📦 Centralized Memory Update

This update relocates all agent session memories from agent-specific directories to a project-isolated structure under `artifacts/`.

### ✨ New Features

-   **Project-Isolated Memory**: Session state files are now stored in `artifacts/{project_id}/{agent_id}/memory/`.
-   **Clean Agent Dirs**: Removed memory storage from `mitra/agents/` to keep core agent definitions separate from session data.

### 🛠️ Changes

-   **Memory Protocol**: Updated `AGENTS.md` and `TREE.md` with the new State Path pattern.
-   **Workflow Synchronization**: Updated all 6 `memory-manager` workflows and mirrored CLI configurations (Claude/Gemini).
-   **Activation Logic**: Enhanced agent startup to automatically create memory subdirectories within the project artifacts folder.

---

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
| **Storage** | Root or random folders | **Structured**: `artifacts/{project_id}/` |

### ✨ New Features

-   **Memory System (Global)**: All 6 agents can now `*save` their session state to JSON and `*load` it later to resume work.
    -   Schema includes: `session_summary`, `key_decisions`, `next_steps`, and `artifacts`.
-   **XML Source of Truth**: Agent behaviors are now defined once in `.agent/workflows/` and propagated to all CLI platforms.
-   **Orchestrator Help**: Added `[0] Help & Guidance` (`*help`) to the Orchestrator for interactive tutorials and validiation.
-   **Agent Registry**: A centralized `mitra/agents/registry.md` now acts as the capabilities catalog.

### 🛠️ Changes

-   **Folder Structure**:
    -   Added `mitra/agents/{agent}/memory/` for state tables.
    -   Standardized workflow paths to `mitra/agents/{agent}/workflows/`.
-   **CLI Configuration**:
    -   Gemini `.toml` files are now strictly generated from the XML source.
    -   Claude `.md` files are now strictly generated from the XML source.
-   **Documentation**:
    -   Updated `AGENTS.md` to be an operational manual.
    -   Updated `CLAUDE.md` and `GEMINI.md` with "Key Features".

### ⚠️ Deprecated / Removed

-   **Legacy Configs**: Removed standalone/divergent configuration files that did not match the `.agent` XML definitions.
-   **Git Awareness**: Removed direct Git operation commands from agent personas; agents now rely on the user for version control.

### 🔮 Under Development (What's Next)

-   **Advanced Tool Calling**: Enabling agents to use more sophisticated tools beyond file I/O.
-   **Agent Builder Service**: A meta-agent to help you design and spawn new custom agents.
-   **Workflow Builder Service**: Visual or conversational tool to define complex agent workflows.
-   **MCP Integration**: Native support for Model Context Protocol to connect with external tools.
-   **RAG & CAG Memory**: Implementing Retrieval-Augmented Generation (RAG) and Content-Augmented Generation (CAG) for handling complex, large-scale project memories.
-   **A2A Protocol**: Enabling A2A Protocol for long-running autonomous tasks.
