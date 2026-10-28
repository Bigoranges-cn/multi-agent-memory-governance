---
name: multi-agent-memory-governance
description: Design, initialize, audit, or extend a private, review-gated memory repository shared by multiple AI assistants, devices, and terminal instances. Use when users need durable cross-session memory with identity isolation, approval workflows, conflict prevention, and safe synchronization. Do not use for ordinary project documentation or raw conversation archiving.
---

# Multi-Agent Memory Governance

Build a durable memory system without treating every conversation as memory or allowing one assistant to overwrite another assistant's local state.

## Choose the operation

- **Design:** Propose the identity hierarchy, sharing boundaries, repository layout, and review workflow. Do not create files unless requested.
- **Initialize:** Inspect the target first, then create only missing approved files. Never overwrite an existing repository or ruleset.
- **Onboard:** Register one assistant/device/terminal identity and its local startup pointer. Keep other instances read-only.
- **Audit:** Check privacy, status fields, proposal state, synchronization cadence, target-file scope, and conflicting claims. Report findings before changing anything.
- **Promote:** Move approved proposal content into its intended durable destination and retain an auditable owner decision.

Read [references/governance-model.md](references/governance-model.md) before designing or changing repository structure. Read [references/security-checklist.md](references/security-checklist.md) before any publication, remote creation, or memory promotion.

## Required workflow

1. Establish the intended scope: private personal use, private team use, or a sanitized public template.
2. Inspect existing files and repository visibility read-only. Treat private-repository 404 responses as ambiguous unless authentication is verified.
3. Declare the writer identity as `assistant__device__instance` and identify the exact target file.
4. Separate information into global shared rules, assistant-family rules, terminal-instance facts, verified project truth, and pending proposals.
5. For a new repository, adapt the files under [assets/repository-template](assets/repository-template). Replace placeholders; do not copy examples as facts.
6. Show the exact target paths and complete proposed durable content. Obtain owner approval immediately before writing.
7. Re-read each target and verify its current version immediately before a write. If it changed, stop and present a revised proposal.
8. Modify only approved targets. Preserve unrelated content and history.
9. Verify the final file set, status fields, repository visibility, working-tree state, and commit scope. Report evidence and unresolved limits.

## Non-negotiable boundaries

- Default to private storage for real memory. A public repository may contain only sanitized methods, templates, and fictional examples.
- Never store credentials, cookies, private keys, verification codes, identity documents, financial or medical records, precise addresses, or unfiltered customer/personnel data.
- Do not store raw conversation transcripts by default. Retain concise, owner-confirmed durable facts and decisions.
- A terminal may directly maintain only its own approved instance file. Wider changes require a review proposal and owner approval.
- Other assistants' files are read-only context and must not be automatically adopted.
- Do not infer that devices share paths, credentials, permissions, tools, or local memory.
- Synchronize on important-session start and durable events, not on every message. Review pending changes at most once daily unless the owner requests otherwise.
- Approval for planning or inspection is not approval to create a public repository, publish, install software, change permissions, or push commits.

## Output expectations

For plans, provide the proposed hierarchy, paths, sharing scope, risks, and approval points. For completed changes, report exact files, commit identifiers when applicable, verification performed, conflicts, and anything intentionally left pending.
