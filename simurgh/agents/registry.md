# Agent Registry

This registry defines the available agents in the Simurgh system and their capabilities. The Orchestrator uses this to route user requests.

## Quick Reference

| Agent | Role | Primary Focus | Trigger |
| :--- | :--- | :--- | :--- |
| **Simurgh** | Orchestrator | Guidance & Routing | Default / `/simurgh:orchestrator` |
| **Zal** | Manager | Planning & Coordination | `/simurgh:persona:manager` |
| **Jamshid** | Architect | Systems & Data | `/simurgh:persona:architect` |
| **Mani** | Designer | UI & UX | `/simurgh:persona:designer` |
| **Kaveh** | Engineer | Technical Specification | `/simurgh:persona:engineer` |

## 🧭 Simurgh (Orchestrator)
- **Role**: All-Seeing Guardian & Guide
- **Capabilities**: Project status, agent routing, context management, memory synthesis.
- **Location**: `simurgh/agents/orchestrator/`
- **Trigger**: Default / `/simurgh:orchestrator`

## 👑 Zal (Manager)
- **Role**: Wise Visionary & Planner
- **Capabilities**: High-level planning, task breakdown, sprint planning, project coordination.
- **Location**: `simurgh/agents/manager/`
- **Trigger**: `/simurgh:persona:manager`
- **Use Case**: New feature requests, project initialization, status checks, planning.

## 🏛️ Jamshid (Architect)
- **Role**: Great Builder
- **Capabilities**: System architecture, database schema design, API contract definition, technical decision making.
- **Location**: `simurgh/agents/architect/`
- **Trigger**: `/simurgh:persona:architect`
- **Use Case**: Database changes, new API endpoints, structural changes, technical reviews.

## 🎨 Mani (Designer)
- **Role**: Master Artist
- **Capabilities**: UI/UX design, user flows, wireframes, mockups, design system management.
- **Location**: `simurgh/agents/designer/`
- **Trigger**: `/simurgh:persona:designer`
- **Use Case**: UI changes, new pages, user experience improvements, accessibility checks.

## ⚡ Kaveh (Engineer)
- **Role**: Master Smith
- **Capabilities**: Technical specification, code review, security audit, documentation.
- **Location**: `simurgh/agents/engineer/`
- **Trigger**: `/simurgh:persona:engineer`
- **Use Case**: Drafting specs, reviewing architecture, auditing security.
