# LTA DataMall Yaak Collection

## Project Overview

This repository is a Yaak API client workspace for the LTA DataMall APIs (Singapore land transport data). It uses Yaak's git sync feature — all `yaak.*.yaml` files in the repo root are managed by Yaak and must remain there.

## Repository Structure

- `yaak.wk_*.yaml` — Workspace definition
- `yaak.fl_*.yaml` — Folder definitions (Public Transport, Traffic, Active Mobility, Geospatial, Electric Vehicle)
- `yaak.rq_*.yaml` — HTTP request definitions (30 API endpoints)
- `yaak.ev_*.yaml` — Environment variables (base_url, AccountKey)
- `docs/` — Reference documentation (LTA DataMall API User Guide PDF)
- `.yaak-encryption-key` — Yaak encryption key (gitignored, must not be committed)

## Key Details

- **Base URL**: `https://datamall2.mytransport.sg/ltaodataservice`
- **Auth**: All requests use an `AccountKey` header, inherited from the workspace. The key is stored in the environment variable `AccountKey`.
- **Yaak CLI**: Use `npx @yaakapp/cli` to interact with the workspace. The workspace ID is `wk_2sfJFtFZDT`.
- **Pagination**: Most APIs return 500 records per call. Use `$skip` query parameter to paginate.

## Important Rules

- Do not move `yaak.*.yaml` files out of the repo root — Yaak's git sync depends on them being there.
- Do not commit `.yaak-encryption-key` or `*.sqlite` files.
- When adding new requests, use the Yaak CLI (`npx @yaakapp/cli request create`) rather than manually creating yaml files.
- The `AccountKey` environment variable contains the actual API key and is encrypted by Yaak — do not store API keys in plaintext.
