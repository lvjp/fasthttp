# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this
repository.

## Project

`fasthttp` is a Rust library crate (early-stage, mostly scaffolding) aiming to be a fast HTTP
package with zero memory allocations in hot paths. Cargo keywords declare a `no_std` intent —
avoid introducing `std`-only dependencies without discussion. Requires Rust 1.96.0+ (edition 2024).
Dual-licensed MIT OR Apache-2.0.

## Commands

```sh
cargo build              # build the library
cargo test               # run all tests
cargo test <test_name>   # run a single test by name (e.g. cargo test it_works)
cargo fmt                # format code
cargo clippy             # lint
```

## Architecture

The crate root is [src/lib.rs](src/lib.rs). Modules are one file per HTTP concept (e.g.
`src/method.rs` for the request method type).

## Conventions (from CONTRIBUTING.md)

- Commit messages follow Conventional Commits: `<type>(<scope>): <subject>`, subject in imperative
  present tense, lowercase, no trailing dot. Types: build, chore, ci, docs, feat, fix, perf,
  refactor, revert, style, test. Commit messages are used to generate the changelog; no line may
  exceed 100 characters. Breaking changes go in the footer starting with `BREAKING CHANGE:`.
- All features and bug fixes must be covered by unit tests.
- All public API items must be documented.
- Code is wrapped at 100 characters.
