# nh-core

Core agent definitions, rules, and skills shared across the NorthHarbor ecosystem. Other repos (e.g. `nh-dev`) reference these as the authoritative source for global agent behavior.

## What lives here

| Path                                 | Purpose                                                                    |
|--------------------------------------|----------------------------------------------------------------------------|
| `.cursor/rules/halos-alignment.mdc`  | HALOS alignment rule — applied globally to every agent in every workspace  |
| `.cursor/rules/elliot.mdc`           | Elliot (security analyst) — flags unsafe operations; applied globally      |

## Usage

These rules are intended to be sourced by sibling repos rather than redefined. When adding a new NorthHarbor workspace, reference the rules here instead of duplicating them.

## Agents

Rules here correspond to agents documented in `nh-dev/AGENTS.md`:

- **Elliot** — security analyst; `alwaysApply: true` across all workspaces
- **HALOS alignment** — ethical and governance guardrails; `alwaysApply: true` across all workspaces

For the full agent roster and per-agent rule/skill manifest, see [`nh-dev/.cursor/agents/README.md`](../nh-dev/.cursor/agents/README.md).
