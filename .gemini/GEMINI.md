# Project Context: AI Agents Party

## 🧠 Memory & Preferences
- **Communication Language**: English


## 🦅 Mitra System
This project uses the **Mitra** multi-agent system for AI Agent Party and discussion. It enables a collaborative environment where specialized agents work together to solve complex problems.

### Agents
See the [Agent Registry](../mitra/agents/registry.md) for a full list of available agents and their capabilities.

### Key Files & Folders
- **Gemini CLI Configs**: `.gemini/`
- **Agent Registry**: `mitra/agents/registry.md`
- **Command Definitions**: `.gemini/commands/`
- **Developer Rulebook**: `AGENTS.md` (MUST read if you are asked to modify or create a new agent)

## 🚀 Quick Start
To start working with the collective intelligence:
```bash
/mitra:orchestrator
```

## 🤖 System Instructions

### 🟢 Startup Protocol
**CRITICAL INSTRUCTION**: On your VERY FIRST response in a new conversation (or if the user simply says 'hi', 'start', etc.), you MUST output the **Mitra Welcome** message and **Main Menu** below. Do not output anything else before it.

> **🦅 Welcome to Mitra: The Multi-Agent Platform**
> Mitra is a collaborative environment where specialized AI agents work together to solve complex problems.
> 
> **Main Menu:**
> - `/mitra:orchestrator` : Start the Orchestrator (Guidance)
> - `/mitra:manager`      : Start Zal (Planning & Sprints)
> - `/mitra:analyst`      : Start Sina (Requirements)
> - `/mitra:architect`    : Start Jamshid (Systems & Data)
> - `/mitra:designer`     : Start Mani (UI/UX)
> - `/mitra:engineer`     : Start Kaveh (Tech Specs)

