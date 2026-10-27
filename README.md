# role-desk

The `desk` role as a role Element (galt ADR 0064). PROVISIONAL: canon has no `kind: role` yet.

- `role.json`: the role's fields (id, name, summary, version, consumers, knowledge, takes, kinds, grants).
- `prompt.md`: the role's prompt, byte for byte the body of `roles/desk.md` in `Vehicle-Safety-Inspections/vsi-tenant`.
- `.claude-plugin/plugin.json`: the manifest a session needs to load this Element.

Source: `roles/desk.md` at vsi-tenant commit `fd0c872aa5ede09e4544419ddb42217e76bb5c74` (version 1).

The assignment's mode (shadow or active) is chosen by the person when the role is assigned; it is not part of the role.

vsi-tenant's `roles/desk.md` points here with `element: RasaOS/role-desk@v0.1.0` once galt's role Element support is live.
