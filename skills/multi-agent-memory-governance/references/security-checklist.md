# Security and publication checklist

Use this checklist before creating a remote repository, changing visibility, promoting memory, or publishing templates.

## Repository boundary

- Confirm whether the destination is private, team-restricted, or public.
- Do not assume that a repository named "private" is actually private.
- Verify the authenticated account and repository owner.
- Treat an unauthenticated 404 for a private repository as ambiguous.

## Content scan

Reject or redact:

- Passwords, tokens, cookies, private keys, recovery codes, and verification codes
- Credential-helper inventory and authentication artifacts
- Personal addresses, identity documents, financial data, and medical data
- Raw customer, employee, or applicant records
- Raw conversation transcripts
- Usernames, absolute home paths, device serials, internal hostnames, and proxy details unless they are intentionally private and necessary
- Private repository URLs, project codenames, and unpublished business details in public packages

Use placeholders such as `<assistant-id>`, `<device-id>`, `<instance-id>`, `<private-repo>`, and `<local-clone-path>` in public templates.

## Authorization

- Separate approval to inspect, create locally, create remotely, publish publicly, install, and push.
- Show the exact files and visibility before publication.
- Do not broaden repository or organization permissions for convenience.
- Do not request credentials in chat. Use an existing credential manager or an approved interactive flow.

## Verification

- Confirm the changed-file list and commit scope.
- Search the package for personal identifiers, private URLs, secrets, and unresolved placeholders.
- Test direct and indirect activation, incomplete requests, non-triggering requests, and unsafe publication cases.
- State what was not verified.

