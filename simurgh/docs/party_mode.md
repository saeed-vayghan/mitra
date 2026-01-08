# Simurgh Party Mode Guide 🎈

**Party Mode** allows you to leverage the collective intelligence of the entire Simurgh agent system in a single collaborative session. Instead of switching personas manually, you can have them all in the room.

## 🚀 Initiation

The Party is hosted by **Simurgh (Orchestrator)**. To start a session, use the Orchestrator command:

```bash
/simurgh:orchestrator
```

Simurgh will present an **Interaction Menu**. Select the **"All Guests (Party)"** option or specific agents to begin the collaboration.

## 🎮 Controlling the Party

Once in Party Mode, the **Collective Consciousness** manages the agents. You control the flow using **Natural Language**.

### 1. Auto-Routing (Default)
Simply ask your question. The system (Simurgh) will automatically select the most relevant agents to answer.

*   **User**: "The API seems slow."
*   **Result**: **Kaveh (Engineer)** and **Jamshid (Architect)** will likely respond to discuss optimization strategies and database query auditing.

### 2. Summoning Agents (@Mention)
You can force a specific agent to respond by mentioning their name or role.

*   **User**: "@Designer, what do you think of this color?"
*   **Result**: **Mani (Designer)** will answer.
*   **User**: "@Manager, are we on track?"
*   **Result**: **Zal (Manager)** will give a status update.

### 3. Cross-Collaboration
You can ask agents to work together on a single problem.

*   **User**: "@Architect and @Engineer, please agree on the API contract."
*   **Result**: Both agents will simulate a dialogue to reach a collaborative conclusion.

## 🎭 The Guest List

For full details on agent capabilities, see the [Agent Registry](../agents/registry.md).

| Agent | Role | Primary Focus | Triggers |
| :--- | :--- | :--- | :--- |
| **Simurgh** | Orchestrator | Guidance & Routing | status, help, where am I |
| **Zal** | Manager | Planning & Coordination | plan, task, timeline, breakdown |
| **Kaveh** | Engineer | Technical Spec & Review | spec, review, audit, explain |
| **Jamshid** | Architect | Systems & Data | database, schema, api, structure |
| **Mani** | Designer | UI & UX | ui, ux, flow, color, layout |

## 💡 Pro Tips

*   **Start with a Plan**: Ask **Zal** to break down your prompt first.
*   **Get a Second Opinion**: After **Kaveh** writes a spec, ask "@Architect" to review it.
*   **Visualize**: Ask **Mani** to describe the UI before **Kaveh** specs the components.
*   **Synthesize**: If the discussion gets too long, ask **Simurgh** to "Summarize the key decisions so far."
