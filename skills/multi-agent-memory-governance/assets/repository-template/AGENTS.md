# AI memory governance

This is a private, review-gated memory repository.

## Authority

The human owner is the final authority. Proposals are not active memory until approved.

## Identity

Every writer declares an assistant family, device ID, and terminal instance ID. The stable identity is `assistant__device__instance`.

## Isolation

- `shared/` contains owner-approved rules for all assistants.
- `assistants/<assistant>/shared.md` contains approved rules for one assistant family.
- `assistants/<assistant>/instances/<device>__<instance>.md` contains facts for one terminal instance.
- A terminal directly maintains only its own approved instance file.
- Other instance files are read-only context and are not automatically adopted.
- Cross-assistant information enters through `review/inbox/`.
- Verified project truth enters `projects/` only after owner approval.

## Writes

Before every durable write, show the exact target and complete change, obtain owner approval, refresh and re-read the target, and stop if its version changed.

Never store credentials, authentication material, raw conversation transcripts, or unfiltered sensitive personal or business data.

Follow `shared/sync-policy.md`.

