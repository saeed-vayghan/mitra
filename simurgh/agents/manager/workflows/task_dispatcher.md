# Task Dispatcher Workflow

## Purpose
This workflow enables the Manager agent to act as the **Dispatcher**, analyzing complex conversations to break them down into specific, actionable tickets assigned to specialized Specialist Agents.

## When to Use
- Invoked by the **Orchestrator** when the party conversation yields actionable items.
- When the user asks "Break this down" or "Make a plan".
- When multiple agents need to work in parallel.

## Workflow Steps

### 1. Analysis
Read the current conversation history and identifying distinct "Intents".
- *Intent*: "We need a new login page." -> **Frontend**.
- *Intent*: "The user database needs a schema update." -> **Database Architect**.

### 2. Analysis & Assignment
Map intents to the **Registry** of available agents (Engineer, Architect, Designer).

### 3. PRD Creation (Mandatory for New Projects)
If this is a new feature or app, generate a `docs/requirements.md` (PRD) first.
1. Define Scope.
2. Define User Stories.
3. Define Tech Stack (agreed by Architect/Engineer).
4. **Wait for User Approval** on the PRD.

### 4. Allocation (The output)
Generate a JSON-structured plan (or markdown table) listing the tasks AFTER PRD is approved.

#### Output Format
```markdown
# Dispatch Plan

| ID | Task | Assgined Agent |
| :--- | :--- | :--- |
| T-1 | Design Login UI | Designer |
| T-2 | Create Auth API | Engineer |
| T-3 | Plan User Schema | Architect |

[NOTIFY: orchestrator] Plan created. Please confirm these assignments.
```

## Rules
- **Granularity**: Break tasks down until they map to a SINGLE workflow.
- **Dependencies**: Note if T-2 depends on T-3.
- **State Update**: Update the Manager's `memory/{YYYYMMDD}-session_latest.json` with these new tasks.
