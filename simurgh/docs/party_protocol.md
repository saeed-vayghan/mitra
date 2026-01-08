# Simurgh Party Protocol

The **Party Protocol** defines the rules of engagement for multi-agent collaboration ("The Party"). It establishes how agents interact, assign tasks, and maintain shared state.

## 1. Roles & Responsibilities

### 🦅 The Host (Orchestrator)
- **Role**: Faciliator and Session Keeper.
- **Responsibilities**:
  - Initiates the party session.
  - Ensures all agents have a chance to contribute.
  - Ensures all agents have a chance to contribute.
  - Invokes the **Manager** when task breakdown is required.

### 📋 The Dispatcher (Manager)
- **Role**: Planner and Task Allocator.
- **Responsibilities**:
  - Listens to the conversation to identify actionable workstreams.
  - **PRD First**: MUST create a `docs/requirements.md` before any coding begins.
  - **PRD First**: MUST create a `docs/requirements.md` before any coding begins.
  - Assigns clear ownership of tasks to specific agents (Engineer, Architect, Designer).

### 🛠️ The Specialists (Engineer, Architect, Designer)
- **Role**: Executors and Scalers.
- **Responsibilities**:
  - Execute assigned tasks using their specialized workflows.
  - Execute assigned tasks using their specialized workflows.
  - Update the shared memory with progress and artifacts.

## 2. Sub-Agent Mapping Rules
*[REMOVED: Agents now own their workflows directly. No mapping required.]*

## 3. Communication Protocol

Agents communicate asynchronously using **Notification Blocks** in their output. The Host (Orchestrator) or System ensures these messages are routed to the target agent.

### Syntax
```text
[NOTIFY: {target_agent}]
{message_content}
```
**Constraint**: Agents must use this block to assign tasks. Natural language chat is for discussion, `[NOTIFY]` is for Action.

### Examples
- **Manager to Engineer**:
  `[NOTIFY: engineer] Please assign the 'API Spec' task. Use your backend-security workflow.`
- **Architect to Designer**:
  `[NOTIFY: designer] The API structure is ready. You can now finalize the mockups.`

## 4. Memory Protocol

All agents MUST maintain state in the `docs/consultancy/` directory of the active project.

### Session File
- **Path**: `docs/consultancy/{YYYYMMDD}-{ProjectName}/{Role}_session.md`.
- **Read**: Agents read this on startup to understand context.
- **Write**: Agents update this after every significant action.

### State Integrity
- Agents must NOT overwrite the entire file blindly. They should read, update specific fields, and write back.
- **Critical Fields**: `tasks`, `shared_context`.
