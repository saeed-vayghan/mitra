# Mitra: The AI Agent Party

**Version**: 2.0.0
**Status**: Stable

Mitra is a multi-agent collective intelligence system designed to facilitate collaborative problem-solving through specialized AI personas.


<div align="center">
  <a href="https://github.com/saeed-vayghan/mitra">
    <picture>
      <img src="mitra/docs/screenshot-01.png">
    </picture>
  </a>
</div>


## Overview
This project defines the "Party Protocol" where agents like the Architect, Engineer, Designer, and Manager collaborate to produce comprehensive consultancy deliverables.


**How to use:**

```bash
# Clone repository
git clone https://github.com/saeed-vayghan/mitra.git
cd mitra

# Config the project
nano mitra/agents/config.yaml

# Run Gemini CLI
gemini


> /mitra:persona:orchestrator

✦ Greetings, Saeed. I am Mitra, the All-Seeing Guardian of this realm. The threads of fate converge here, under my watchful eye, as we weave the destiny of Project Mitra.

  I have established our sanctum at docs/consultancy/project-test-cmds/. All wisdom gathered and designs forged shall be preserved there.

  How shall we proceed?

  Menu Options:
   * *party : [A] Party Mode (Collaboration)
   * *help  : [0] Help & Guidance (Tutorial)
   * *analyst: [1] Call Sina (Analyst)
   * *manager: [2] Call Zal (Manager)
   * *architect: [3] Call Jamshid (Architect)
   * *engineer: [4] Call Kaveh (Engineer)
   * *designer: [5] Call Mani (Designer)
   * *context: [C] Initialize Project Context
   * *save   : [S] Save Session State
   * *load   : [L] Load / List Memories
   * *menu   : [M] Redisplay Menu

```

### More to learn about Mitra
- [Features & Guide](GUIDE.md)


## ❤️ Inspiration & Philosophy
Mitra was built with love, drawing massive inspiration from:
- [BMAD-METHOD](https://github.com/bmad-code-org/BMAD-METHOD)
- [GitHub Spec Kit](https://github.com/github/spec-kit)
- [Fission-AI OpenSpec](https://github.com/Fission-AI/OpenSpec)

We thank these projects for paving the way.

**The "Why"**: While there are many incredible tools for *coding* (Cursor, Copilot, Windsurf), Mitra fulfills the need for a **Scalable Consultant AI Framework**. It is designed to be:
- **Customizable**: Easy to extend with new agents.
- **Consultancy-Only**: Focusing entirely on high-level Architecture, Requirements, and Design, leaving the implementation joy to the human.

## Learn how to use Mitra
- [Features & Guide](GUIDE.md)

## Documentation
- [Agent Registry](mitra/agents/registry.md)
- [Operational Manual](AGENTS.md)
- [Changelog](CHANGELOG.md)

---

## 🆚 Comparison with Similar Tools

Mitra stands out by strictly adhering to a **Consultancy Model**, where AI Agents allow *you* to be the implementer while they handle the high-level strategy and specification.

| Feature | **Mitra** | **BMAD-METHOD** | **OpenSpec** | **GitHub Spec Kit** |
| :--- | :--- | :--- | :--- | :--- |
| **Core Philosophy** | **Consultancy-First:** "We Plan, You Build." | **Agile AI-Driven:** "Context-Engineered Development." | **Spec-Driven (SDD):** "Align before you build." | **Spec-Driven (SDD):** "No Vibe Coding." |
| **Agent Role** | **Consultants:** Strictly non-coding. Strategy & Specs only. | **Implementation:** 19+ agents including Devs/Testers. | **Workflow Guides:** Agnostic agents guided by `AGENTS.md`. | **Task Executors:** Execute "Specify -> Implement" phases. |
| **Workflow** | **Party Mode:** Collaborative brainstorming + specialized routing. | **4-Phase:** Analysis -> Planning -> Solutioning -> Implementation. | **Proposal-Based:** Draft -> Review -> Merge Specs. | **Iterative:** Specify -> Plan -> Task -> Implement. |
| **Memory/State** | **Long-Term JSON:** Explicit `*save`/`*load` of full session context. | **Context Engineering:** Sharding and Codebase flattening. | **File-Based:** `specs/` vs `changes/` folders. | **Living Docs:** `Constitution.md` + evolving Specs. |
| **Architecture** | **XML Source of Truth:** Synced to Gemini/Claude CLIs. | **Scale-Adaptive:** Quick/Enterprise tracks + Expansion Packs. | **CLI + Slash Commands:** `openspec init`, `/openspec:proposal`. | **Templates + CLI:** `specify` CLI + Pre-built templates. |
| **Key Differentiator** | **Human-in-the-Loop Implementation:** AI handles 100% of thinking. | **End-to-End Automation:** Agents handle code, tests, and flattening. | **Change Management:** Explicit proposal/archive lifecycle. | **Principles-First:** `Constitution.md` governs all decisions. |

### Why Mitra?
Choose Mitra if you want the **intelligence** of a Principle Architect and Manager but prefer to maintain full control over the **code implementation** yourself. It is designed to augment your decision-making, not replace your coding joy.
