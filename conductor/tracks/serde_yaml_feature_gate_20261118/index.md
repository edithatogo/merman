# Conductor planning: qualify YAML parser migration in feature-gated Merman

[Specification](spec.md) · [Plan](plan.md) · [Metadata](metadata.json)

Serde/serde_json are already used appropriately. serde_yaml is optional for full-config and xtask; careless replacement would affect Mermaid parity and WASM footprint.

This track is supplementary to existing repository governance; implementation approval and reviews remain with the established maintainers.
