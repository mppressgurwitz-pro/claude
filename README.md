# claude

Engineering documentation workspace for the `mppressgurwitz-pro/claude`
repository.

## Current repository state

This repository currently contains documentation only. As of this update, no
application source code, package manifests, service definitions, CLIs, APIs,
migrations, or deployment configuration are tracked in Git.

Because there is no runnable code yet, there are no install, build, test, or
deployment commands for developers to execute. When code is added, update this
README in the same change to document the real setup and verification path.

## Documentation index

- [`docs/engineering-documentation-runbook.md`](docs/engineering-documentation-runbook.md)
  - How to keep engineering documentation current as the repository evolves.

## Developer workflow

Use this lightweight workflow until the repository gains a project-specific
toolchain:

1. Inspect the current branch and changed files:

   ```bash
   git status --short
   git diff --name-only origin/main...HEAD
   ```

2. Update documentation alongside any source change that introduces or changes:
   - public interfaces such as APIs, commands, configuration, or data contracts;
   - developer setup, build, test, deploy, or troubleshooting steps;
   - operational workflows, alerts, failure modes, or recovery procedures.
3. Verify documentation against source code and checked-in configuration before
   committing. Do not describe behavior that cannot be found in the repository.
4. Keep documentation concise and link to deeper runbooks instead of duplicating
   the same guidance across multiple files.

## Common pitfalls

- **No setup command exists yet.** This is expected while no project manifest or
  source code is tracked.
- **Docs mention a missing codepath.** Treat that as stale documentation and
  update or remove the claim in the same pull request that changes the code.
- **New code lands without docs.** Add the minimum useful docs: intent, entry
  points, required configuration, example commands, and known failure modes.
