# Memory synchronization policy

Status: pending owner approval
Approved: pending

## Default cadence

Use event-triggered synchronization, not per-message synchronization.

- Read the minimum relevant approved memory once at an important session start.
- Do not synchronize ordinary chat, brainstorming, intermediate debugging, or unconfirmed assumptions.
- Prepare a proposal when a durable owner-confirmed rule, decision, correction, capability, or project-state change occurs.
- At a major work-stage end, propose one concise continuity update instead of a transcript.
- Review waiting durable changes at most once daily unless the owner requests otherwise.

## Before a write

1. Refresh the source.
2. Re-read the exact target.
3. Verify its current version.
4. Modify only the approved target.
5. Stop and request renewed approval if the target changed.

