# Contributing to merman

Merman implements headless Mermaid parsing and rendering in Rust, with related platform bindings. Contributions should improve source-backed semantics, structural parity, reliable interfaces and reproducible verification.

## Before you start

Read [README.md](README.md), [AGENTS.md](AGENTS.md) and [CONTEXT.md](CONTEXT.md). Check existing issues and pull requests and identify the affected diagram family or binding. Preserve the upstream attribution in [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md). Keep unrelated local work intact and use focused branches.

For bugs, provide the affected version or commit, environment, minimal reproduction, expected result and observed result. For a substantial proposal, describe the use case and compatibility impact before expanding implementation scope. Use existing issue templates when offered.

## Development and validation

Use the pinned [Rust toolchain](rust-toolchain.toml), workspace configuration and the relevant [CI workflows](.github/workflows). Follow the applicable parity and release-quality documents linked from the README; they define the accepted checks and residuals for each surface. Report the exact commands selected and their observed results rather than assuming one command qualifies all bindings.

Add a minimal diagram or binding example that demonstrates the changed behaviour. Prefer parser, model, layout and render evidence from the pinned Mermaid implementation. Keep comparator normalization narrow and non-semantic. Record browser-dependent text measurement, fonts, HTML labels and similar residuals explicitly; do not hide them through fixture-specific tuning.

For rendering changes, inspect relevant SVG structure and visual output. For bindings, exercise the affected host boundary and callback or resource lifetime. Preserve existing platform and release requirements, and distinguish local checks from unexecuted matrix entries.

## Pull requests

Create a focused branch from the current `main` branch and submit a pull request to this repository. Link the relevant issue or existing project task, explain the resulting behaviour, and update affected examples and documentation. Keep unrelated changes in separate pull requests.

Report executed commands, outcomes and the commit they validate. Identify unavailable checks and remaining limitations explicitly. Follow the repository's existing review and automated-check requirements; retain required gates and current ownership. Address findings and verify the final head before integration. Repository changes do not themselves authorise a release or external operational action.

## Security, rights and conduct

Follow the [security policy](https://github.com/edithatogo/.github/blob/main/SECURITY.md). Use private vulnerability reporting if available; otherwise request a private contact without publishing vulnerability details. Keep credentials, personal information and restricted source material out of issues, fixtures, logs and artifacts.

Read the [existing licence](LICENSE) and preserve attribution and third-party terms. Follow the [code of conduct](https://github.com/edithatogo/.github/blob/main/CODE_OF_CONDUCT.md) and keep technical discussions respectful.

## Basis for this guide

This guide follows [GitHub's contribution-guideline guidance](https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/setting-guidelines-for-repository-contributors) and the contribution-process and testing principles in [OpenSSF Best Practices](https://www.bestpractices.dev/en/criteria). It does not assert certification.
