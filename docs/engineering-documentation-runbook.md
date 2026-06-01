# Engineering Documentation Runbook

Use this runbook when source changes alter how developers, operators, or
integrators understand the repository.

## Purpose

Engineering documentation should answer three questions:

1. What does this code or workflow do?
2. How does a developer use, test, or operate it safely?
3. What constraints or failure modes should the next maintainer know?

Keep documentation close to the truth in source code. If the repository does not
contain the behavior yet, do not document it as implemented.

## When documentation must change

Update docs in the same pull request when a change affects:

- public interfaces: APIs, command-line flags, event payloads, schemas,
  configuration keys, exported functions, or data contracts;
- developer workflows: setup, local development, tests, code generation,
  migrations, release, or deployment;
- operations: scheduled jobs, queues, alerts, dashboards, incident response,
  rollback, backup, or recovery;
- common pitfalls: permissions, environment variables, missing dependencies,
  rate limits, destructive operations, or idempotency constraints.

If a change is purely internal and has no external workflow impact, a short note
in the relevant module README or code comment may be enough.

## Verification checklist

Before writing or updating docs:

1. Identify changed files with:

   ```bash
   git diff --name-only origin/main...HEAD
   ```

2. Read the source, configuration, and tests that define the behavior.
3. Confirm the documented command or workflow can be run in a clean checkout, or
   clearly state why it cannot be run yet.
4. Remove stale claims instead of preserving outdated guidance.
5. Keep examples minimal and executable. Prefer real paths and flags from the
   repository.

## Recommended doc locations

- `README.md`: repository overview, setup, most common commands, and links.
- `docs/`: cross-cutting workflows, operational runbooks, architecture notes,
  and troubleshooting guides.
- Module-level `README.md`: subsystem-specific usage when a directory owns a
  clear runtime or interface.
- Inline comments: only for non-obvious decisions that are hard to express in
  external docs.

Prefer updating an existing page when it already owns the topic. Create a new
page only when the content has a distinct audience or workflow.

## Minimum content for a new workflow

When documenting a new workflow, include:

- intent: why the workflow exists;
- entry points: commands, URLs, jobs, or files involved;
- required configuration: environment variables, config files, permissions, and
  safe defaults;
- example usage: copy-pasteable command or request examples;
- verification: expected success signal and a failure signal;
- constraints: destructive actions, idempotency, rate limits, data ownership, or
  rollback notes;
- troubleshooting: common errors with likely causes and next checks.

## Pull request checklist

Use this checklist for documentation-only changes:

- [ ] The docs describe only behavior verified in the repository.
- [ ] The most relevant existing doc was updated instead of creating a duplicate.
- [ ] Examples use real file paths, commands, flags, or configuration names.
- [ ] Setup and troubleshooting notes are concise enough to scan.
- [ ] The PR summary lists the codepaths or workflows covered.
