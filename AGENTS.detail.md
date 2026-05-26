# AGENTS.md

## Purpose

This repository tracks the `alive-agent` onboarding wizard used for OpenClaw role bring-up.

## Safe change rules

- Preserve the pre-`Proceed?` no-op safety guarantee.
- Do not make changes that expose or echo Slack tokens or pairing secrets.
- Keep onboarding steps explicit, ordered, and reviewable.
- Prefer additive verification output over opaque behavior.
- Treat the workspace runtime copy and the GitHub copy as needing reconciliation whenever one changes.

## Expected files

- `alive-agent`
- `README.md`
- `README.source.md`
- `AGENTS.md`

## Verification guidance

Before claiming the program is safe or ready after edits:

1. run shell lint if available
2. review the selection and confirmation flow
3. verify the script still requires explicit confirmation before making changes
4. verify Slack prompts remain silent and are not logged
5. verify documented dependencies still match the script

## Change workflow

- Prefer branch + PR workflows for non-bootstrap changes.
- Keep the README aligned with observable script behavior.
- If behavior changes materially, update both `README.md` and `README.source.md` or replace `README.source.md` with a refreshed source export.

## Sensitive areas

- token handling
- pairing approval steps
- onboarding phase transitions
- session-materialization checks
- gateway restart behavior
