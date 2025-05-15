# Contributing to MCP Dart Codegen

First off, thank you for taking the time to contribute!  We value the community and want to make contributing as easy and transparent as possible.

---

## Table of contents

1. [Code of Conduct](#code-of-conduct)
2. [Getting started](#getting-started)
3. [Development workflow](#development-workflow)
4. [Coding guidelines](#coding-guidelines)
5. [Commit message conventions](#commit-message-conventions)
6. [Pull-request checklist](#pull-request-checklist)

---

## Code of Conduct

This project adheres to the [Contributor Covenant](https://www.contributor-covenant.org/) Code of Conduct. By participating, you are expected to uphold this code. Please report unacceptable behaviour to <opensource@cloudwalk.io>.

---

## Getting started

1. **Fork** the repository and clone your fork locally.
2. Install the [Dart SDK](https://dart.dev/get-dart) ‑ version 3.3 or later.
3. Retrieve dependencies:

   ```shell
   $ dart pub get  # from the repo root – works thanks to the mono-repo layout
   ```

4. Run the test-suite to make sure everything passes before you start:

   ```shell
   $ dart test ./packages/...
   ```

---

## Development workflow

```text
             ┌────────────┐
             │  main      │  ← protected
             └─────▲──────┘
                   │ PR
            feature/<topic>
```

* Create a topic branch off `main`: `git checkout -b feature/my-change`.
* Make commits following the [conventional commit](#commit-message-conventions) style.
* Keep your branch up-to-date with `main` (rebase preferred).
* Open a pull-request – the CI pipeline will run tests and lints automatically.

---

## Coding guidelines

* **Format** your code before committing: `dart format .`.
* **Analyse** for warnings / errors: `dart analyze` (no hints allowed).
* **Test**: `dart test ./packages/...` – all tests must pass.
* **Public API docs** are required for any new public class, method, or field.
* Avoid breaking changes when possible. If unavoidable, document them thoroughly in the PR description.

---

## Commit message conventions

We follow the **[Conventional Commits](https://www.conventionalcommits.org/)** specification.

```
type(scope?): subject

body?  # wrapped at 72 chars

footer?
```

Example:

```
feat(codegen): add support for custom output extensions
```

Accepted *types* include but are not limited to:

* **feat** – a new feature
* **fix** – a bug fix
* **docs** – documentation only changes
* **chore** – tooling / maintenance
* **refactor** – code change that neither fixes a bug nor adds a feature
* **test** – adding / correcting tests

---

## Pull-request checklist

Before marking your PR ready for review, ensure that:

- [ ] The **CI** checks are all green.
- [ ] `dart analyze` reports **zero** issues.
- [ ] **Tests** covering new functionality have been added / updated.
- [ ] Public API has **documentation comments**.
- [ ] The PR description clearly explains **why** and **how**.
- [ ] You added yourself to **`AUTHORS`** if this is your first contribution.

Thanks for helping improve MCP Dart Codegen 🎉 