# alive-agent

`alive-agent` is an interactive terminal onboarding wizard for bringing an OpenClaw role agent to a live-ready state with the current deterministic flow.

This repository packages the current script and its usage notes so the program can be versioned, reviewed, and improved in GitHub.

## What it does

The script helps an operator:

- choose an unfinished role to onboard
- choose runtime options such as model, mode, and pool
- optionally configure Slack during the same flow
- review a final plan before anything changes
- execute the standard onboarding sequence in order
- print lightweight verification outputs
- restart the OpenClaw gateway at the end

Before the final confirmation prompt, the wizard is intentionally no-op and safe to exit.

## Source of truth today

The current operational source script lives in the OpenClaw workspace here:

- `/root/.openclaw/workspace-agent-k/scripts/alive-agent`
- `/root/.openclaw/workspace-agent-k/scripts/alive-agent.README.md`

This repository is intended to hold the GitHub-tracked version of that program.

## Repository contents

- `alive-agent` — the shell script
- `README.md` — repo overview and operator-facing summary
- `README.source.md` — the fuller source README copied from the current workspace
- `AGENTS.md` — repo-specific guidance for agents

## How to run

```bash
./alive-agent
```

Or from its current runtime location:

```bash
/root/.openclaw/workspace-agent-k/scripts/alive-agent
```

## Dependencies

The script currently expects:

- `python3`
- `openclaw`
- `jq`

## Safe operating notes

- Exiting before the final `Proceed?` confirmation makes no changes.
- After `Proceed?`, the script performs real onboarding actions.
- Slack token entry is interactive and intentionally silent.
- Use extra caution when resuming partially onboarded roles.

## Next improvements worth considering

- classify roles as clean, resume, or risky
- provide a resume-only mode
- persist operator choices to a log or artifact
- harden publishing workflow so the GitHub copy stays aligned with the runtime copy
