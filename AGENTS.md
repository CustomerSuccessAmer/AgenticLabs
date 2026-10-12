# AgenticLabs agent guide

## Team workflow

The organization-wide rules are in
[`eva-next-infrastructure/docs/development-workflow.md`](https://github.com/CustomerSuccessAmer/eva-next-infrastructure/blob/develop/docs/development-workflow.md).
They bind coding agents exactly as they bind people. In this repository:

- Before starting any task, refresh this file: `git fetch origin && git checkout develop && git pull --ff-only`.
- If the person you work for is not an owner, they have read access only. Do not ask for write
  access; fork instead and open the pull request from the fork:
  `gh repo fork CustomerSuccessAmer/<repo> --clone=false`, add the fork as a remote, push the branch
  there, then `gh pr create --repo CustomerSuccessAmer/<repo> --base develop --head <login>:<branch>`.
  Tell the person the pull request link; an owner reviews and merges it.
- A new repository in the organization starts with a `develop` branch, `.github/CODEOWNERS` naming
  its creator, the pull request template, and this section in `AGENTS.md` with `CLAUDE.md` loading it.
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
