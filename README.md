# claude

This repository currently contains the initial project scaffold only.

## Current state

- Source code: not present.
- Runtime services or public APIs: not present.
- Package manager manifests: not present.
- Test, lint, build, or deployment commands: not present.
- Operational runbooks: not present because there are no deployed components in
  this repository yet.

The only tracked project file at this revision is this `README.md`. Keep future
documentation grounded in committed source files and configuration rather than
planned or assumed behavior.

## Developer setup

There are no application dependencies to install yet. To inspect the repository:

```bash
git clone <repository-url>
cd claude
git status
```

When source code is added, document the exact setup path in this README or in a
focused page under `docs/`. Include:

1. Required runtimes and package managers.
2. Environment variables, with safe examples in `.env.example` when applicable.
3. Commands for install, local development, tests, linting, builds, and deploys.
4. Common failure modes and the fastest way to diagnose them.

## Documentation workflow

Prefer updating existing documentation before creating new pages. Add new docs
only when a topic has a distinct owner or workflow, for example:

- `docs/setup.md` for multi-step local setup.
- `docs/architecture.md` for service boundaries and data flow.
- `docs/runbooks/<service>.md` for operational procedures.
- `docs/troubleshooting.md` for recurring developer or production issues.

Every technical document should state:

- which codepaths or configuration files it covers;
- the intended audience and usage scenario;
- concrete commands or examples that can be verified locally;
- constraints, unsupported cases, and known pitfalls.

Avoid documenting behavior that is not implemented in the repository.
