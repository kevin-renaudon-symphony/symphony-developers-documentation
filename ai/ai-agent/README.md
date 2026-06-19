# What is an AI Agent?

## Overview

An **AI agent** is a specialized service account designed to expose AI-powered applications to end users. Unlike a standard bot, an AI agent is often backed by a Large Language Model (LLM) and can reason, access contextual data, and take actions on behalf of the user — all within the boundaries of the platform's security model.
Within Symphony, AI agents can be accessed not only in regular internal and external rooms, but also on a specific secure channel: the **Agent streams**.

---
## Types of AI Agents

Many different sort AI agents can be created within Symphony:
- **Melody** - Symphony's built-in agent that can help any user with daily messaging activities with summaries, catchups... 
- **Your agents** - Your agents, customized according to your user needs with access to your tools. These agents can be created and managed seamlessly thanks to Symphony's AI agent studio, or built using Symphony's APIs.
- **Community agents** - Agents built by Symphony partners or the Symphony's community that can be found via Symphony's directory.

---

## AI Agent Capabilities

### 1. AI Agent stream

In addition to standard rooms, an AI agent can interact with users in dedicated **AI Agent Room** — a strictly private, encrypted space between the user and the AI agent. No other user can join, enforcing confidentiality. This room can also act as a persistent session context, allowing the agent to maintain conversation history and improve its responses iteratively.
As this stream is strictly a 1-1 room between the user and the AI agent, the AI can safely use it to disclose user specific information or perform actions on-behalf-of the user as only 

### 2. Contextual Awareness via On-Behalf-Of (OBO) APIs

One of the most powerful features of Symphony AI agents is their ability to access a user's conversation history to provide grounded, source-traceable answers. This access is:

- **Strictly bounded**: the agent can never access more data than the user themselves can see — room memberships, information barriers, and sharing restrictions are all enforced by design.
- **Cryptographically controlled**: to read an encrypted room, the agent must be granted the appropriate OBO permissions *and* the requesting user must be a participant in that conversation.
- **Administrator-controlled**: all permissions are configured by the customer's administrator through standard Symphony admin tools.

Required OBO permissions include: `Act as user`, `Get user messages`, `List user streams`, and optionally `Get user attachments`.

### 3. Configurable Behaviour

Studio agents can be tailored through:

- **System prompts** — define the agent's core behaviour and persona.
- **Prompt templates** — predefined forms that guide users and improve interaction quality.
- **LLM model selection** — choose from Symphony-provided models or connect the agent to a customer-owned LLM.
- **Tools** — connect to Symphony-native tools or external systems via MCP (Model Context Protocol) servers.
- **Permissions** — grant only the data access the agent actually needs.



---

## How an AI Agent Differs from a Standard Bot

| Feature | Standard Bot | AI Agent |
|---|---|---|
| LLM-powered reasoning | ✗ | ✓ |
| Assistant Room support | ✗ | ✓ |
| Per-user enablement | ✗ | ✓ |
| On-behalf-of data access | ✗ | ✓ |
| Tool / MCP integration | Limited | ✓ |

---

## Lifecycle

When an agent is created via the AI Studio, the **AI agent platform** automatically detects it and spins up a new agent instance — users with the agent installed can start interacting with it immediately.

Prompt compilation follows a just-in-time principle: conversation context and additional data are assembled at query time and **never stored unencrypted** on Symphony's servers.

---

## Compliance

All interactions in an Assistant Room carry the same compliance guarantees as any other Symphony room:

- **Content export** — messages are archived.
- **Audit trails** — all actions are tracked.
- **Compliance review** — supervisors can review prompts and responses.
- **Automatic removal** — agents and users are removed from rooms when deactivated.
- **AI-specific traces** — reasoning steps, tool calls, model used, and user consent events are automatically recorded, supporting forensic investigations if needed.

---



## Summary

An AI agent is the building block of Symphony's AI platform. It brings LLM intelligence into the secure, encrypted Symphony environment while preserving the platform's core principles: end-to-end encryption, strict information boundaries, administrator control, and full compliance auditability.
