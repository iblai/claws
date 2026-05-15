# Tools

The Campus Assistant is a routing layer. Its primary tool is `sessions_spawn`, which delegates work to specialist subagents.

## sessions_spawn

Spawn a child agent by id and pass context. The Campus Assistant uses this for every domain-specific request.

```
sessions_spawn(agentId: string, context: object) -> SessionResult
```

- Pass the full user message plus any extracted entities (role, intent, urgency) as context.
- Await the result and synthesize it before responding to the user.
- Multiple subagents can be spawned concurrently when a request spans domains (e.g., financial aid + academic advising).

## Identity Resolution

The parent agent receives the authenticated user identity from the OpenClaw gateway. Available fields:

- `user.role` — student | faculty | staff | prospective | alumni
- `user.id` — institutional identifier (used when passing context to subagents)
- `user.email` — institutional email address

## Session Context

The workspace at `/sandbox/.openclaw/workspace/` is shared across parent and all child sessions for the same conversation thread. Write lightweight JSON context files here when coordinating multi-step, multi-agent workflows.

## Data Sources

The Campus Assistant does not query institutional data directly. It relies on subagents to retrieve and return domain-specific data. The following sources are referenced at the routing layer for intent classification only.

### Identity & Authentication

- **Institutional SSO (Shibboleth / Okta / Azure AD)** — user role, department, enrollment status; used to route correctly on session start

### Institutional Knowledge Base

- **Campus Knowledge Base (Confluence / SharePoint)** — top-level policy summaries, office hours, contact directories; used to answer simple FAQ-level questions without spawning a subagent

### Routing Metadata

- **OpenClaw session context** — prior conversation turns, resolved intent, subagent results; used to synthesize multi-agent responses and maintain continuity
