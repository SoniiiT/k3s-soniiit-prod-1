# Project knowledge

`.ai-context/` contains compact generated facts and curated lifecycle guidance. Source code and explicit project rules remain authoritative. Generated summaries must not replace inspecting the YAML being changed.

- `manifest.json`, `project-map.md`, `architecture.md`, `conventions.md`, `dependencies.md`, and `indexes/` are analysis outputs.
- `knowledge/` records feature lifecycle guidance, risks, decisions, and business-rule status.
- Secret values are never copied here. Sensitive paths are named only when needed to explain a risk or dependency.
- Findings marked `inferred` are relationships derived from resource references, not confirmed business rules.
