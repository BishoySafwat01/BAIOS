# Communication Protocol

## Purpose

This document defines the communication model between architectural layers, executive components, AI agents, memory modules, and external integrations within Bishoy AI Operating System (BAIOS).

The objective is to establish predictable communication patterns, eliminate responsibility overlap, and maintain a consistent flow of information throughout the system.

---

## Design Principles

Communication within BAIOS follows four principles:

- Every request has a single owner.
- Every decision has a responsible authority.
- Information flows through defined channels.
- AI agents communicate through the architecture rather than directly whenever possible.

---

## Communication Flow

The normal flow of execution is:

```

User
↓

Chief of Staff
↓

Relevant Hub

↓

Specialized AI Agent

↓

Memory / External Integrations

↓

Agent Response

↓

Chief of Staff

↓

User

```

The Chief of Staff acts as the central coordinator for operational requests.

---

## Strategic Decisions

Strategic decisions follow a different communication path.

```

User

↓

Mission Control

↓

Chief of Staff

↓

Relevant Hub

↓

AI Agent

```

Mission Control determines strategic direction before operational planning begins.

---

## Memory Access

AI agents do not own information.

Persistent knowledge is retrieved from the Memory Layer.

```

AI Agent

↓

Memory Layer

↓

Validated Context

↓

AI Agent

```

This ensures that every component works with the same source of truth.

---

## External Services

Communication with external services must occur through the Integration Layer.

Example:

```

Chief of Staff

↓

Todoist Integration

↓

Todoist API

```

Direct communication between AI agents and external services is discouraged unless explicitly defined.

---

## Agent-to-Agent Communication

Direct communication between AI agents should be minimized.

When coordination is required, communication should be routed through the responsible Hub or the Chief of Staff.

Example:

```

Research Agent

↓

Research Hub

↓

Chief of Staff

↓

Professional Hub

↓

CV Expert

```

This approach simplifies auditing, debugging, and responsibility management.

---

## Error Handling

If an agent cannot complete its responsibility, it must:

1. Report the failure.
2. Explain the reason.
3. Return available evidence.
4. Request further instructions if necessary.

Agents should never fabricate missing information.

---

## Communication Rules

Every interaction should include:

- Objective
- Context
- Required output
- Available constraints
- Responsible component

No component should operate without sufficient context.

---

## Architectural Benefits

This communication model provides:

- Clear ownership
- Reduced coupling
- Consistent execution
- Better observability
- Easier debugging
- Scalable architecture

