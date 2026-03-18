# nh-core

Core agent definitions, rules, and skills shared across the NorthHarbor ecosystem. Other repos (e.g. `nh-dev`) reference these as the authoritative source for global agent behavior.

## What lives here

| Path                                         | Purpose                                                                      |
|----------------------------------------------|------------------------------------------------------------------------------|
| `.cursor/rules/halos-alignment.mdc`          | HALOS alignment summary — applied globally to every agent in every workspace |
| `.cursor/rules/elliot.mdc`                   | Elliot (security analyst) — flags unsafe operations; applied globally        |
| `.cursor/rules/offer-follow-up-actions.mdc`  | Proactively offer to run next steps the user could do                        |

## How to use in a new repo

Add a `.cursor/agents/README.md` to your repo and reference nh-core rules by relative path. Do not copy the files.

```markdown
## Global (always applied)

| Rule                    | Path                                                    | Scope                                                        |
|-------------------------|---------------------------------------------------------|--------------------------------------------------------------|
| HALOS alignment         | `../nh-core/.cursor/rules/halos-alignment.mdc`          | `alwaysApply: true` — human primacy, attribution, guardrails |
| Elliot (security)       | `../nh-core/.cursor/rules/elliot.mdc`                   | `alwaysApply: true` — security checks on every conversation  |
| Offer follow-up actions | `../nh-core/.cursor/rules/offer-follow-up-actions.mdc`  | `alwaysApply: true` — proactively offer to run next steps    |
```

Then add app-specific agents below that section as needed.

## Policy

HALOS alignment in these rules is a **consumer summary**. The authoritative HALOS contract and spec live in [`../halos/`](../halos/). All agent behavior across the ecosystem flows from that definition — nh-core does not redefine it.

## Repos using nh-core

| Repo       | Manifest                               |
|------------|----------------------------------------|
| `nh-dev`   | `.cursor/agents/README.md`             |
| `halos`    | `.cursor/agents/README.md`             |
| `breezy`   | `.cursor/agents/README.md`             |
