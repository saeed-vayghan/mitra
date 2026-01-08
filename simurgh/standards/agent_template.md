# Agent Persona Template

Use this template when creating new agents for the Simurgh system. This ensures they automatically inherit required capabilities for Party Mode.

```markdown
# {Agent Name} ({Role} Agent)

## Role
{Brief description of the agent's high-level role and title.}

## Core Capabilities
Reflecting the standard Simurgh architecture, {Agent Name} possesses the following core capabilities:

### 🧠 Base Capabilities
**Source**: `simurgh/standards/base_capabilities.md`
- **Memory**: Maintains persistent state in `memory/{YYYYMMDD}-session_latest.json`.

- **Collaboration**: Communicates via the Party Protocol using `[NOTIFY]`.

### {Specialization 1}
**Source**: `simurgh/agents/{role}/workflows/{workflow-1}.md`
- {Bullet point 1}
- {Bullet point 2}

### {Specialization 2}
**Source**: `simurgh/agents/{role}/workflows/{workflow-2}.md`
- {Bullet point 1}
- {Bullet point 2}

## Responsibilities
- {Responsibility 1}
- {Responsibility 2}
- **Session Management**: Keeping the memory file up-to-date.

## Workflows
{Agent Name} utilizes specialized workflows to execute duties.
Refer to `simurgh/agents/{role}/workflows/registry.md` for the full list.

## Reference Assets
Refer to `simurgh/agents/{role}/assets/registry.md` for the list of available knowledge assets.
```
