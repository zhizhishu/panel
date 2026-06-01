---
sidebar_position: 3
---

# Testing And Validation

## Current Repository Scope

This fork is the Remnawave documentation repository. Validation for this branch focuses on:

- Docusaurus type checking.
- Docusaurus production build.
- GitHub fork/branch availability.
- Remote clone smoke testing.

It does not validate a runtime orchestrator yet because the companion app has not been created.

## Local Checks

Run from the repository root:

```bash
npm ci
npm run typecheck
npm run build
```

Expected result:

- TypeScript passes.
- Docusaurus builds the static site.
- Future docs are included under the generated sidebar.

## Termius Real Host Checks

Target host requested for smoke tests:

- `isrco-hk`

Current observed environment:

- Debian Linux.
- `git` is available.
- `docker` is available.
- `node` and `npm` are not currently installed on the host.

Recommended remote smoke test after pushing `future`:

```bash
rm -rf /tmp/remnawave-panel-future
git clone --branch future --single-branch https://github.com/zhizhishu/panel.git /tmp/remnawave-panel-future
cd /tmp/remnawave-panel-future
git log -1 --oneline
test -f docs/future/orchestrator-plan.md
test -f docs/future/implementation-classification.md
test -f docs/future/testing-and-validation.md
```

If Docker image pulls are acceptable on the host, a containerized build can be used without installing Node globally:

```bash
docker run --rm -v /tmp/remnawave-panel-future:/work -w /work node:24-bookworm bash -lc "npm ci && npm run typecheck && npm run build"
```

## Future Product Validation

When the companion orchestrator exists, testing should expand to:

- Remnawave API connection test.
- Read-only node/profile/host/squad discovery.
- Generated Xray JSON schema validation.
- Generated profile diff preview.
- Dry-run push mode.
- Apply to a test node.
- Node restart and health check.
- Snell Docker/systemd snippet generation.
- Snell subscription entry generation.
- Client import tests for Surge and other Snell-compatible clients.
