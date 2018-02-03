# Contributing to SHELF

**Looking for a first issue?** You might want to start out by looking at
issues tagged "good first issue". These are issues that, while important,
will probably require less context regarding the SHELF codebase and
should make good jumping-off points for potential contibutors. Furthermore,
issues tagged as "easy" as well as "good first issue" are likely to be the
most well-suited for Rust beginners.

## Table of Contents

+ [What do I need to know before contributing?](#what-do-i-need-to-know-before-contributing)
    - [Code of Conduct](#code-of-conduct)
    - [Licensing](#licensing)
+ [Conventions & Style Guides](#conventions--style-guides)
    - [Git Conventions](#git-conventions)
        * [Pull Requests](#pull-requests)
        * [Commit Messages](#commit-messages)
    - [Coding Style](#coding-style)
        * [Tools to assist with coding style](#tools-to-assist-with-coding-style)

## What do I need to know before contributing?

### Code of Conduct

This project adheres to the Contributor Covenant [code of conduct].
By participating, you are expected to uphold this code.
Please report unacceptable behavior to [eliza@elizas.website].

[code of conduct]: CODE_OF_CONDUCT.md
[eliza@elizas.website]: mailto:eliza@elizas.website

### Licensing

SHELF is licensed under the [MIT](LICENSE) open-source license. By contributing
code to SHELF, you agree to waive all copyright claims on your contribution
and allow it to be distributed under this license.

## Conventions & Style Guides

### Git Conventions

#### Pull requests

In order to be accepted and merged, a pull request must meet the following conditions.

##### Pull requests MUST

+ Build successfully on [Travis](https://travis-ci.org/hawkw/alarm)
+ Include RustDoc comments for any public-facing API functions or types
+ Include tests for any added features
+ Reference any closed issues with the text "Closes #XX" or "Fixes #XX" in the pull request description

##### Pull requests MUST NOT

+ Include any failing tests.
+ Have any outstanding changes requested by a reviewer.

#### Commit messages

Commit messages should follow the [Angular.js Commit Message Conventions](https://github.com/conventional-changelog/conventional-changelog/blob/a5505865ff3dd710cf757f50530e73ef0ca641da/conventions/angular.md). We use [`clog`](https://github.com/clog-tool/clog-cli) for automatically generating changelogs, and commit messages must be in a format that `clog` can parse.

It is recommended that contributors read the linked documentation for the Angular commit message convention in full –– it's not that long. For the impatient, here are some of the most important guidelines:

##### Commit messages MUST

+ Be in present tense
+ Follow the form `<type>(<scope>): <subject>`
    + where `<type>` is one of:
        * **feat**: A new feature
        * **fix**: A bug fix
        * **docs**: Documentation only changes
        * **style**: Changes that do not affect the meaning of the code (white-space, formatting, missing
        semi-colons, etc)
        * **refactor**: A code change that neither fixes a bug or adds a feature
        * **perf**: A code change that improves performance
        * **test**: Adding missing tests
        * **chore**: Changes to the build process or auxiliary tools and libraries such as documentation
        generation
    + and `<scope>` (optionally) specifies the specific element or component of the project that was changed.

##### Commit messages MUST NOT

+ Include lines exceeding 100 characters

##### Commit messages MAY

+ Include the text `[skip ci]` if changing non-Rustdoc documentation.
  + This will cause Travis CI to skip building that commit.
  + Commits which change RustDoc documentation in `.rs` source code files
    should still be built on CI -- `[skip ci]` should only be used for commits
    which change external documentation files such as `README.md`
  + Commits which change configuration files for tools not used by Travis may
    also skip the CI build, at the discretion of the committer.


### Code Style

Rust code should:
+ Follow the [Rust style guidelines](https://github.com/rust-lang/rust/tree/master/src/doc/style/style) and the guidelines in the ["Effective Rust" section](https://doc.rust-lang.org/book/effective-rust.html) of the Rust Book, except when contradicted by this document.
  + In particular, it should...
    + ...be indented with 4 spaces
    + ...not end files with trailing whitespace
    + ...follow the [Rust naming conventions](https://github.com/rust-lang/rust/tree/master/src/doc/style/style/)
+ Not exceed 80 characters per line.

### Tools to Assist With Coding Style

#### rustfmt

[`rustfmt`](https://github.com/rust-lang-nursery/rustfmt) is a tool for automatically formatting Rust source code according to style guidelines. This repository provides a [`rustfmt.toml`](rustfmt.toml) file for automatically configuring `rustfmt` to use our style guidelines.

`rustfmt` may be installed by running

```bash
cargo install rustfmt
```

and invoked on a crate by running

```bash
cargo fmt
```

Additionally, there are `rustfmt` plugins [available](https://github.com/rust-lang-nursery/rustfmt#running-rustfmt-from-your-editor) for many popular editors and IDEs.

`rustfmt` may also be added as a [git pre-commit hook](https://git-scm.com/book/uz/v2/Customizing-Git-Git-Hooks) to ensure that all commits conform to the style guidelines.
