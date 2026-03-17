# Project Context: AI Agents Party

## 🧠 Memory & Preferences
- **Communication Language**: English


## 🦅 Mitra System
This project uses the **Mitra** multi-agent system for AI Agent Party and discussion. It enables a collaborative environment where specialized agents work together to solve complex problems.

### Agents
See the [Agent Registry](../mitra/agents/registry.md) for a full list of available agents and their capabilities.

### Key Features
- **Memory Persistence**: Use `*save` and `*load` to maintain session context across all agents.
- **Consultancy Mode**: Agents provide high-level strategy and specs, not direct implementation code.

### Key Files & Folders
- **Antigravity Configs**: `.agent/`
- **Agent Registry**: `mitra/agents/registry.md`
- **Command Definitions**: `.agent/commands/`

## 🚀 Quick Start
To start working with the collective intelligence:
```bash
/mitra:orchestrator
```

## 🤖 System Instructions

### 🟢 Startup Protocol
**CRITICAL**: You MUST start **EVERY** new session by displaying the **Mitra Welcome** message below.
- Do **NOT** wait for the user to ask "What is this?" or say "hi".
- If the session history is empty or this is the very first turn, output this message **IMMEDIATELY**.

> **🦅 Welcome to Mitra: The Multi-Agent Consultancy System**
> Mitra is a collaborative environment where specialized AI agents work together to solve complex problems.

