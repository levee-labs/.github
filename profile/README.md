<div align="center">

# Levee Labs

**Operational standards that move with the work.**

[Website](https://levee.biz/) · [Team Start Here (Levee access)](https://github.com/levee-labs/levee-platform-docs/blob/main/guides/onboarding/start-here.md) · [Developer Guide (Levee access)](https://github.com/levee-labs/levee-platform-docs/blob/main/guides/DEVELOPER_ONBOARDING.md)

</div>

Levee helps hospitality teams turn brand standards and operating procedures
into daily execution, inspection, quality, and learning workflows.

| Standardize | Operate | Improve |
|---|---|---|
| Organize policies, standards, and SOPs | Run inspections and operational workflows | Turn findings into learning and better standards |

## Engineering at Levee

Levee is developed across focused, independently versioned repositories. For
cross-service work, engineers collect only the repositories they need inside a
local directory named `agent-workplace`.

`agent-workplace` is a **multi-repository workspace container**. It is not a
monorepo, Git submodule parent, or Git worktree. Each child repository keeps its
own branches, history, tests, and release path; workspace-level instructions
provide the shared context needed to coordinate changes across services.

## Levee team members: start here

The following links and repository require authenticated Levee organization
access.

```bash
mkdir -p ~/development/agent-workplace
cd ~/development/agent-workplace

git clone git@github.com:levee-labs/levee-platform-docs.git docs
./docs/guides/onboarding/sync-agent-workspace.sh --apply .
./docs/guides/onboarding/verify-agent-coordination.sh .
```

Then follow the private [role-based onboarding guide](https://github.com/levee-labs/levee-platform-docs/blob/main/guides/onboarding/role-guide.md)
to clone the component repositories required for your work.

For an existing workspace, safely pull and apply the latest shared agent
contract:

```bash
./docs/guides/onboarding/sync-agent-workspace.sh --pull .
```

The updater validates the private pack, preserves local task records and
unrelated Claude settings, and refuses conflicting local instruction changes
before writing.

## One coordination loop

```text
READ → CLAIM → DECIDE → ISOLATE → EXECUTE → VERIFY → HAND OFF
```

- Claude Code starts at the workspace root, imports `AGENTS.md` through
  `CLAUDE.md`, and runs `/context` to confirm the instructions are loaded.
- Codex starts at the same root and reads the same `AGENTS.md` contract.
- Every substantial task records ownership, plan, progress, evidence, and
  handoff in the shared task ledger before branch or worktree changes begin.

Read the private [agent coordination workflow](https://github.com/levee-labs/levee-platform-docs/blob/main/guides/AGENT_COORDINATION_WORKFLOW.md)
for the full decision flow and safety boundaries.
