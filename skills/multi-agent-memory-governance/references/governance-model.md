# Governance model

Use this model when designing, initializing, onboarding, auditing, or promoting memory.

## Identity hierarchy

Every writer has three stable identifiers:

1. Assistant family
2. Device ID
3. Terminal instance ID

The combined identity is `assistant__device__instance`. A device is not an assistant, and two terminals on one device are not assumed to share local state.

## Information scopes

| Scope | Intended content | Typical destination |
| --- | --- | --- |
| Global | Owner-approved rules shared by every assistant | `shared/` |
| Assistant family | Rules shared only by instances of one assistant | `assistants/<assistant>/shared.md` |
| Terminal instance | Local paths, tools, constraints, and continuity | `assistants/<assistant>/instances/<device>__<instance>.md` |
| Project | Verified state and decisions for one project | `projects/` |
| Proposal | Information awaiting owner review | `review/inbox/` |
| Archive | Superseded material retained for audit | `archive/` |

Information does not become wider in scope merely because another assistant can read it.

## Authority and lifecycle

The human owner is the final authority.

1. An assistant observes a possible durable fact or rule.
2. It classifies the intended scope and sensitivity.
3. It prepares a proposal with source, destination, confidence, risks, and review status.
4. The owner approves, revises, or rejects it.
5. Approved content is promoted to the intended destination.
6. The proposal records the decision and remains available for audit.

Pending proposals are not active memory.

## Synchronization cadence

- At an important session start, read the minimum relevant approved files once.
- Do not synchronize ordinary conversation, brainstorming, intermediate debugging, or unconfirmed assumptions.
- Propose durable changes when an owner-confirmed rule, decision, capability, correction, or project-state change occurs.
- At a major stage end, prefer one concise handoff over a transcript.
- Review waiting durable changes at most once daily unless the owner requests a different cadence.

## Conflict prevention

Immediately before a write:

1. Fetch or otherwise refresh the target source.
2. Re-read the exact target.
3. Verify its current version or content hash.
4. Apply only the approved change.
5. If the target changed, stop and present a revised proposal.

Branch protection is useful but does not replace behavioral scope controls.

