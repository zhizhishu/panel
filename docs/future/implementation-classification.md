---
sidebar_position: 2
---

# Implementation Classification

## Category A: Documentation Fork

Repository:

- `zhizhishu/panel`

Purpose:

- Record product direction.
- Classify architecture.
- Keep future notes close to official Remnawave docs.

What it can change:

- Documentation only.

What it cannot change:

- Runtime Remnawave UI.
- Backend APIs.
- Node behavior.

## Category B: Companion Orchestrator

Recommended first real product.

Purpose:

- Provide the beginner button-flow UI.
- Generate advanced Xray configs.
- Push Remnawave Config Profiles through the Remnawave API.
- Manage external Snell node inventory.
- Compose mixed subscriptions when appropriate.

Why this first:

- Does not fork Remnawave internals.
- Lower merge maintenance cost.
- Lets the config generator mature independently.
- Avoids forcing Snell into Xray-core.

## Category C: Remnawave Frontend Extension

Repositories:

- `remnawave/frontend`

Purpose:

- Add native route wizard screens inside Remnawave UI.

Needed when:

- Companion UX is proven.
- The operator wants a single integrated UI.

Risk:

- Requires staying compatible with upstream Remnawave UI changes.

## Category D: Remnawave Backend Extension

Repositories:

- `remnawave/backend`

Purpose:

- Add durable orchestration models.
- Add APIs for presets, generated profile ownership, Snell inventory, and composed subscriptions.

Needed when:

- Companion app needs native persistence and first-class permissions.

Risk:

- Higher coupling with Remnawave release cadence.

## Category E: Remnawave Node Extension

Repositories:

- `remnawave/node`

Purpose:

- Native node-level runtime features.

Not recommended for Snell MVP.

Reason:

- Remnawave Node is Xray-core based.
- Snell v5 should run as a separate service first.
- Native Snell support would require service supervision, config rendering, status checks, logs, credentials, subscriptions, and accounting outside Xray.

## Recommended Roadmap

### Phase 0: Research and Classification

Deliverables:

- Documentation fork with future plan.
- Repository boundary map.
- MVP requirements.

### Phase 1: Companion MVP

Deliverables:

- Orchestrator UI.
- Remnawave API connection.
- Server inventory.
- Snell inventory.
- Route wizard.
- Xray JSON generator.
- Diff and validation before push.

### Phase 2: Operational Features

Deliverables:

- SSH-assisted Snell deployment, optional.
- Health checks.
- Rule pack updates.
- Import/export.
- Backup.

### Phase 3: Deep Remnawave Integration

Deliverables:

- Frontend route wizard.
- Backend orchestration APIs.
- Optional upstream contribution path.

### Phase 4: Native Snell, Only If Justified

Deliverables:

- Node-level Snell supervisor.
- Snell config lifecycle.
- Snell stats strategy.
- Client-specific subscription generation.

This phase should happen only if external Snell management is not enough.
