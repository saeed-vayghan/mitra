# Simurgh: The AI Agent Party

**Version**: 2.0.0
**Status**: Stable

Simurgh is a multi-agent collective intelligence system designed to facilitate collaborative problem-solving through specialized AI personas.

## Overview
This project defines the "Party Protocol" where agents like the Architect, Engineer, Designer, and Manager collaborate to produce comprehensive consultancy deliverables.

## ❤️ Inspiration & Philosophy
Simurgh was built with love, drawing massive inspiration from:
- [BMAD-METHOD](https://github.com/bmad-code-org/BMAD-METHOD)
- [GitHub Spec Kit](https://github.com/github/spec-kit)
- [Fission-AI OpenSpec](https://github.com/Fission-AI/OpenSpec)

We thank these projects for paving the way.

**The "Why"**: While there are many incredible tools for *coding* (Cursor, Copilot, Windsurf), Simurgh fulfills the need for a **Scalable Consultant AI Framework**. It is designed to be:
- **Customizable**: Easy to extend with new agents.
- **Consultancy-Only**: Focusing entirely on high-level Architecture, Requirements, and Design, leaving the implementation joy to the human.

## Learn how to use Simurgh
- [Features & Guide](GUIDE.md)

## Documentation
- [Agent Registry](simurgh/agents/registry.md)
- [Operational Manual](AGENTS.md)
- [Changelog](CHANGELOG.md)

---

## 🆚 Comparison with Similar Tools

Simurgh stands out by strictly adhering to a **Consultancy Model**, where AI Agents allow *you* to be the implementer while they handle the high-level strategy and specification.

| Feature | **Simurgh** | **BMAD-METHOD** | **OpenSpec** | **GitHub Spec Kit** |
| :--- | :--- | :--- | :--- | :--- |
| **Core Philosophy** | **Consultancy-First:** "We Plan, You Build." | **Agile AI-Driven:** "Context-Engineered Development." | **Spec-Driven (SDD):** "Align before you build." | **Spec-Driven (SDD):** "No Vibe Coding." |
| **Agent Role** | **Consultants:** Strictly non-coding. Strategy & Specs only. | **Implementation:** 19+ agents including Devs/Testers. | **Workflow Guides:** Agnostic agents guided by `AGENTS.md`. | **Task Executors:** Execute "Specify -> Implement" phases. |
| **Workflow** | **Party Mode:** Collaborative brainstorming + specialized routing. | **4-Phase:** Analysis -> Planning -> Solutioning -> Implementation. | **Proposal-Based:** Draft -> Review -> Merge Specs. | **Iterative:** Specify -> Plan -> Task -> Implement. |
| **Memory/State** | **Long-Term JSON:** Explicit `*save`/`*load` of full session context. | **Context Engineering:** Sharding and Codebase flattening. | **File-Based:** `specs/` vs `changes/` folders. | **Living Docs:** `Constitution.md` + evolving Specs. |
| **Architecture** | **XML Source of Truth:** Synced to Gemini/Claude CLIs. | **Scale-Adaptive:** Quick/Enterprise tracks + Expansion Packs. | **CLI + Slash Commands:** `openspec init`, `/openspec:proposal`. | **Templates + CLI:** `specify` CLI + Pre-built templates. |
| **Key Differentiator** | **Human-in-the-Loop Implementation:** AI handles 100% of thinking. | **End-to-End Automation:** Agents handle code, tests, and flattening. | **Change Management:** Explicit proposal/archive lifecycle. | **Principles-First:** `Constitution.md` governs all decisions. |

### Why Simurgh?
Choose Simurgh if you want the **intelligence** of a Principle Architect and Manager but prefer to maintain full control over the **code implementation** yourself. It is designed to augment your decision-making, not replace your coding joy.
