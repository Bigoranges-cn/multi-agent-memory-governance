# Multi-Agent Memory Governance

A privacy-first Skill for designing and operating a private, review-gated memory repository across AI assistants, devices, and terminal instances.

It helps users keep durable rules and verified project facts synchronized without copying raw conversations, sharing credentials, or allowing one terminal to overwrite another terminal's local state.

## What it provides

- Three-part identities: `assistant__device__instance`
- Separate global, assistant-family, terminal-instance, project, and proposal scopes
- Owner approval before durable writes
- Target version checks and conflict stopping
- Event-triggered synchronization instead of per-message synchronization
- Sanitized repository templates and a publication safety checklist

## Package layout

```text
plugin.json
skills/
  multi-agent-memory-governance/
    SKILL.md
    agents/openai.yaml
    references/
    assets/repository-template/
```

The first release is instruction-only and uses tools already available to the host. It does not require an MCP server, API key, or hosted service.

## Privacy model

Use this public repository only for the reusable method and templates. Store real identities, device paths, project facts, and memory in a separate private repository controlled by the user.

Never copy a private memory repository into a public fork.

## Development status

Version `0.1.0` is a local release candidate. Review and test it before publishing or adding it to a marketplace.

## License

MIT. See [LICENSE](LICENSE).


