# role-desk

**Version:** 0.2.1 · `rasa.module.role.desk` · public

The **Desk** role (`desk`) as a RasaOS role module. The operator's private desk in vsi-tenant. It acts for Chazz with keep-moving powers, pulls what it needs from the fleet, and asks him for anything only a person can decide.

| File | What it is |
|---|---|
| `role.json` | The role's fields (id, name, summary, version, consumers, knowledge, takes, kinds, grants). galt publishes them to `/tenant_config/roles/desk`. |
| `prompt.md` | The role's prompt, byte for byte the body of `roles/desk.md` in vsi-tenant. |
| `.claude-plugin/plugin.json` | The plugin manifest, which makes the repo loadable into a session with `--plugin-dir`. |
| `rasa.json` | The Element manifest: `kind: module`, with the role's id and version under `rasa`. |
| `bin/check-role` | The release gate. |

Role version **1**, from `roles/desk.md` at vsi-tenant `fd0c872`.

## Loading it

- **As an agent's brain:** `galt agent new <name> --brain RasaOS/role-desk@v0.2.1`. galt reads `role.json` and `prompt.md`. There is no role assignment this way, so no grants.
- **As the source of the published role:** the tenant's `roles/desk.md` becomes the one line `element: RasaOS/role-desk@v0.2.1`. After a person runs Publish roles, every agent with role `desk` loads this Element. galt's scheduler supports this; it advertises `role_elements` (galt ADR 0064).
- **Public:** any computer can fetch it. No vault token is needed.

## Changing the role

Until the tenant's `roles/desk.md` points here, that file is what Publish roles reads, and this repo is a snapshot of it. vsi-tenant's `/role` skill (`bin/role-element`) keeps them together; see `CLAUDE.md`.
