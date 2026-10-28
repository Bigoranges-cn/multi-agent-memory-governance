# Runtime validation

Versions tested: direct Skill install `v0.1.0`; marketplace plugin install `v0.1.1`

This is a sanitized record of the first local runtime test. It contains no real user, device, project, path, or private-repository data.

## Environment boundary

- The Skill was installed from the public `v0.1.0` tag into a local Codex Skills directory.
- No real memory repository was opened or modified.
- No test artifact was pushed during execution.
- All scenario identities were fictional.

## Discovery and invocation

| Check | Result |
| --- | --- |
| Appeared in the next-turn Skills catalog | Pass |
| Explicit `$multi-agent-memory-governance` invocation selected the Skill | Pass |
| Required governance reference loaded | Pass |
| Design mode remained read-only | Pass |

## Scenario

The prompt requested a private memory design for two fictional assistants, `alpha-assistant` and `beta-assistant`, on `home-laptop` and `office-desktop`.

Observed behavior:

- Produced four separate `assistant__device__instance` identities
- Separated global, assistant-family, terminal-instance, project, proposal, and archive scopes
- Kept pending proposals distinct from active memory
- Required owner approval before durable writes
- Used event-triggered synchronization rather than per-message synchronization
- Did not access or infer any real repository, username, device, project, or local path

## Result

Pass. No runtime defect was observed in the first read-only Design-mode test.

## Marketplace installation and fresh-conversation discovery

The public repository was added as a Codex marketplace source pinned to `v0.1.1`. Codex resolved the marketplace catalog, installed the plugin, and reported it as installed and enabled.

The earlier direct Skill installation was moved to a recoverable backup before the marketplace plugin was installed, preventing two active copies from affecting discovery.

| Check | Result |
| --- | --- |
| Marketplace source resolved from the public Git repository | Pass |
| Catalog discovered plugin version `0.1.1` | Pass |
| Plugin installed and enabled through the Codex plugin CLI | Pass |
| Installed manifest and Skill entrypoint matched the pinned source by SHA-256 | Pass |
| Fresh conversation loaded the Skill from the marketplace plugin cache | Pass |
| Fresh conversation selected read-only Design mode | Pass |
| Governance reference loaded from the marketplace plugin cache | Pass |
| No repository or file was created by the scenario | Pass |

The fresh-conversation prompt requested only a private multi-assistant, multi-device memory design. The response kept assistant, device, and terminal identities separate; treated proposals as inactive until owner approval; required target refresh before writes; used event-triggered rather than per-message synchronization; and prohibited credentials and raw transcripts.

## Result

Pass. Marketplace installation, next-conversation discovery, explicit Skill use, reference loading, and read-only behavior were all observed without accessing or modifying a real memory repository.

