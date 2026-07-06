# claude

Engineering documentation for this repository.

## Current repository state

This repository currently contains documentation only. At the time this README
was updated, no runtime source code, package manifests, service entrypoints,
deployment configuration, or tests were tracked in Git.

Because there is no executable subsystem yet, there are no setup commands,
public APIs, operational runbooks, or troubleshooting steps to document beyond
the repository-level guidance below.

## Repository layout

```text
.
`-- README.md
```

When application code is added, keep documentation close to the code it
explains. Prefer updating this README or an existing focused document before
creating another top-level page.

## Documentation expectations

For each new subsystem, document:

- Intent: what problem the subsystem solves and who uses it.
- Architecture: key modules, data flow, storage, and external integrations.
- Interfaces: CLI commands, HTTP routes, background jobs, schemas, or public
  functions that other developers depend on.
- Operations: setup, required environment variables, local run commands,
  deployment notes, monitoring, and rollback or recovery steps.
- Verification: tests, smoke checks, sample inputs, and expected outputs.
- Pitfalls: common failure modes, constraints, and safe recovery actions.

Avoid documenting behavior that has not been verified against source code.
If a feature is planned but not implemented, label it as planned rather than
describing it as current behavior.

## Adding developer setup instructions

When the repository gains executable code, add a setup section that includes:

1. Required tool versions.
2. Environment variables, with a committed `.env.example` if configuration is
   required.
3. Dependency installation commands.
4. Local run commands.
5. Test, lint, and build commands.
6. Troubleshooting notes for known installation or runtime failures.

Use copy-pasteable examples and keep commands non-interactive where possible so
humans and automation can run them consistently.
