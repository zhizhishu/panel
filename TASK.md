# Current Task

Goal: Fork Remnawave locally and on GitHub, create a `future` branch, and classify a future architecture for a beginner-friendly multi-server orchestrator that keeps Remnawave managing Xray while Snell v5 runs separately.

Completed:
- Forked `remnawave/panel` to `zhizhishu/panel`.
- Cloned fork to `C:\Users\echo\Downloads\claude\remnawave-panel-fork`.
- Created local `future` branch.
- Confirmed `remnawave/panel` is a Docusaurus docs repository (`@remnawave/docs`), not the production frontend/backend code.
- Added future architecture documentation under `docs/future`.
- Confirmed Termius bridge can reach the `isrco-hk` window and target xterm.
- Ran an initial `isrco-hk` environment check: Debian host, `git` and `docker` available, `node`/`npm` not installed.
- Pushed `future` branch to `https://github.com/zhizhishu/panel/tree/future`.
- Ran `isrco-hk` remote smoke test against the pushed branch.
- Ran `isrco-hk` Docker validation with `node:24-bookworm`: `npm ci`, `npm run typecheck`, and `npm run build` completed successfully.

Next:
- For implementation, fork or create repositories for:
  - companion orchestrator UI/API, recommended first MVP, or
  - `remnawave/frontend`, `remnawave/backend`, and possibly `remnawave/node` if doing direct integration.

Verification:
- `gh auth status` confirmed GitHub account `zhizhishu`.
- `gh repo list remnawave` confirmed relevant upstream repos: `frontend`, `backend`, `node`, `templates`, `panel`, `subscription-page`.
- Termius V5 bridge health check passed on `127.0.0.1:37663`.
- `isrco-hk` xterm id used for current testing: `2`.
- `isrco-hk` cloned `future` at commit `20e7a65` and found all Future docs.
- `isrco-hk` Docker build generated static Docusaurus files successfully.

Risks:
- Directly modifying `remnawave/panel` will only change docs. It will not add runtime UI features to Remnawave.
- Snell v5 should remain external in the proposed MVP because Remnawave Node is Xray-core based.
- `isrco-hk` does not currently expose local `node`/`npm`; remote build testing may require Docker or installing runtime tooling.
- Docusaurus build reports upstream broken-anchor warnings unrelated to the new Future docs:
  - `/docs/changelog/remnawave-panel` -> `/docs/awesome-remnawave#backup-restore`
  - `/docs/learn/xray-json-advanced` -> `#addVirtualHostAsOutbound`
