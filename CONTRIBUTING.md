# Contributing at Levee

Levee team members begin with the private
[Developer Start Here guide](https://github.com/levee-labs/levee-platform-docs/blob/main/guides/onboarding/start-here.md).
Repository-local instructions, manifests, source, tests, and CI remain the
authority for each component.

## Workspace model

Use `agent-workplace` as a local multi-repository workspace container. It is
not a monorepo: every child repository keeps independent Git history, branches,
tests, and releases.

Install the shared Claude Code/Codex contract from the private docs repository:

```bash
./docs/guides/onboarding/sync-agent-workspace.sh --apply .
./docs/guides/onboarding/verify-agent-coordination.sh .
```

Use `--pull` on the sync script for later updates.

## Before substantial work

1. Read workspace `AGENTS.md`, `REPO_MAP.md`, and the active task index.
2. Inspect the target repository's status, remotes, worktrees, and current
   instructions.
3. Create or claim a task README with exact scope, ownership, base SHA, paths,
   authorization limits, plan, and verification gates.
4. Resolve overlapping file or behavior claims before editing.
5. Use a fresh branch and isolated worktree from the repository's verified base
   for tracked changes when the shared checkout is dirty or in use.
6. Keep the task README current as implementation, evidence, and delivery state
   change.
7. Run target-repository checks, the workspace verification gate, and a
   fresh-context correctness review before committing.

Never place credentials, customer identifiers, private payloads, or raw agent
memory/session exports in GitHub. A commit, PR, merge, deployment, and runtime
verification are separate states; external actions require the authorization
defined by the task and repository.

Read the private [full coordination workflow](https://github.com/levee-labs/levee-platform-docs/blob/main/guides/AGENT_COORDINATION_WORKFLOW.md)
for the decision flow and handoff contract.
