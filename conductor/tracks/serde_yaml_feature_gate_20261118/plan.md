# Implementation plan: Conductor planning: qualify YAML parser migration in feature-gated Merman

- [ ] Freeze `full-config`, `xtask` and no-default feature compile graph, binary sizes and exact Mermaid YAML directive fixtures before changes.
- [ ] Evaluate maintained parsers, MSRV, licence, release/security history and transitive dependency cost; compare nonempty mappings, nested arrays, anchors/aliases, duplicate keys, tags, NaN/null, malformed large input and error location/format.
- [ ] Add failing regression for current `unwrap_or(Value::Null)` conversion fallback if it silently discards data, then decide explicit strictness/compatibility through existing Mermaid parity review.
- [ ] Keep existing host-neutral/WASM/Typst profile and JS import budget; no `serde_yaml` or heavier replacements in minimal builds.
- [ ] Route approved implementation through existing `docs/workstreams`/AGENTS owner, update feature documentation, run `cargo test`/clippy/format, profile-size and pinned Mermaid golden/differential tests on exact head; no-go is acceptable.
