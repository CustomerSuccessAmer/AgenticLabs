# AgenticLabs agent guide

## Team workflow

The organization-wide rules are in
[`eva-next-infrastructure/docs/development-workflow.md`](https://github.com/CustomerSuccessAmer/eva-next-infrastructure/blob/develop/docs/development-workflow.md).
They bind coding agents exactly as they bind people. In this repository:

- `.github/CODEOWNERS` names the owners. Anyone else changes this repository only through a pull
  request an owner approves.
- `develop` runs in Development and `main` runs in Production. Branch from an up-to-date `develop`,
  open the pull request against `develop`, and never push to `develop` or `main` directly.
- Deploy, publish, or migrate in Development only from an up-to-date `develop`, after the change is
  merged. Never from a feature branch or a worktree.
- A migration changes only the schema this repository owns, stays compatible with the code in
  `develop`, and carries its own role grants.
- Production changes follow
  [change management](https://github.com/CustomerSuccessAmer/eva-next-infrastructure/blob/develop/docs/change-management.md):
  a written plan Axel approves first, then the release pull request `develop` → `main`.
