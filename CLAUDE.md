# OpenWolf

This project uses OpenWolf for context management. The always-on rules live in `.claude/rules/openwolf.md`; the hooks handle bookkeeping (anatomy index, memory log, read tracking) automatically.

For the full operating protocol (session handoff, memory discipline, bug logging), load the `openwolf` skill, or read `.wolf/OPENWOLF.md`. Regenerate the session handoff with `/handoff`.


# Shared project context

Use `.ai-context/` as the canonical project context. Read the relevant map, architecture, conventions, dependencies, and lifecycle guidance before making repository changes.

The generated context is advisory; source files and explicit project instructions are authoritative. Never persist or repeat secret values found in manifests.
