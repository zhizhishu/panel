# Log

## 2026-06-01

- Forked `remnawave/panel` to `zhizhishu/panel`.
- Cloned fork locally at `C:\Users\echo\Downloads\claude\remnawave-panel-fork`.
- Created `future` branch.
- Confirmed this repository is the Remnawave Docusaurus documentation repository, not the runtime frontend/backend implementation.
- Added Future documentation describing the companion orchestrator approach and implementation classification.
- Checked Termius V5 bridge and confirmed `isrco-hk` session/xterm access.
- Ran initial `isrco-hk` environment check: Debian, `git` and `docker` present, `node`/`npm` absent.
- Pushed `future` branch to `zhizhishu/panel`.
- Verified on `isrco-hk` that the pushed `future` branch can be cloned and contains all Future docs.
- Verified on `isrco-hk` with Docker `node:24-bookworm` that `npm ci`, `npm run typecheck`, and `npm run build` complete successfully.
- Noted Docusaurus upstream broken-anchor warnings during build; they are not introduced by the Future docs.
