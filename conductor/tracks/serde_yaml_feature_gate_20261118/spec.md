# Specification: Conductor planning: qualify YAML parser migration in feature-gated Merman

## Current implementation
- Root `Cargo.toml` declares `serde` derive, `serde_json` (`preserve_order`), `serde_yaml`, JSON5 and Serde/WASM binding adapters. `merman-core` gates `serde_yaml` and `json5` on `full-config`; `xtask` uses YAML values for fixtures/config.
- `crates/merman-core/src/inline_config.rs` uses `serde_yaml::from_str::<serde_yaml::Value>` for full-config inline YAML, followed by `serde_json::to_value(raw).unwrap_or(Value::Null)`. Evaluate explicit error propagation and loss-of-type handling: silent `Null` fallback requires a test-backed policy.
- `serde_yaml` is the format parser; Serde cannot replace the native Mermaid lexer, diagram parser, JSON5, layout or SVG renderer. Existing WASM slimming deliberately omits YAML in minimal profiles.

## Decision
Candidate maintained parsers are `serde-saphyr` and `yaml_serde`; no unconditional swap. Preserve Mermaid compatibility, Unicode, YAML numeric/tag/alias behaviour and the feature matrix. Ensure `full-config` remains opt-in and the Typst/pure-WASM profile does not gain host imports or JS dependencies. Never alter the renderer to compensate for YAML differences.
