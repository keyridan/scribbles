---
title: "Cargo Sweeten: Ensure awesome Rust libraries"
categories:
- rust
- idea
---
Here are some things in Rust's ecosystem that I really like:

0. The awesome people
1. Well documented libraries by awesome people
2. Automation to help awesome people focus on awesome stuff

I would like to add something to that.

## My ideas so far

- [Good practices for crates](https://pascalhertleif.de/artikel/good-practices-for-writing-rust-libraries/)
- [Elegant APIs in Rust]({% post_url 2016-07-21-elegant-apis-in-rust %})
- [Doc string style]({% post_url 2016-08-17-machine-readable-inline-markdown-code-cocumentation %})
- [Writing guides with doc tests]({% post_url 2016-12-28-teaching-libraries %})

## Cargo Sweeten

A new `cargo sweeten` subcommand that automatically tries to ensure the Rust library it is executed in is top-notch, i.e.:

- `Cargo.toml` has
	- well-formatted authors
	- license
	- descriptions
	- repository OR website OR documentation (more is better)
	- Readme fiel name
	- keywords
- `.gitignore` and `.editorconfig`
- `README.md` with
	- Code example(s)
	- Link to API docs (ideally docs.rs)
	- Contribution section
- Has a license
- Has CI integration
- Is documented (`#[deny(missing_docs]`)
- Passes `clippy`
- Has unit and/or integration tests
- Has `examples/` with code that builds and/or `docs/` with guides
- Is formatted with `rustfmt` (`diff == 0`)

Running `cargo sweeten` will check which of these requirements are and try to add what is missing in an interactive manner.