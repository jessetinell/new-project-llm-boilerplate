# Start here

You are in a new project folder, copied from the `template/` folder of the boilerplate repo. Follow these steps to set the project up, then delete this file.

## Setup steps

1. **Check the copy:** this folder should contain these template files (not the boilerplate repo's own `README.md`, `AGENTS.md` and `template/` folder) and a fresh `git init`.
2. **Read** `STANDARDS.md` and `COST_CAUTIONS.md` fully.
3. **Write `BRIEF.md`** from the user's idea. Keep their words; leave unknown sections out rather than guessing.
4. **Ask only what's blocking** (at most a few questions, in one go). Use the defaults in `STANDARDS.md` for everything else.
5. **Fill the placeholders** (`{{…}}`) in `AGENTS.md`, `README.md`, `HOSTING.md` and the project section of `COST_CAUTIONS.md`. Create `API.md` only if the project has an API (see `STANDARDS.md`). Never delete `COST_CAUTIONS.md`.
6. **Scaffold the app** with the default stack (or the user's override), smallest working version first.
7. **Check:** `grep -rn "{{" *.md` returns nothing; the app runs locally.
8. **Delete this file.** Then summarize what was set up, what's next, and anything the human must do in a dashboard (list it in `HOSTING.md`).

Never deploy or change anything live without asking.

## What's here

| File | Purpose | Edit? |
|---|---|---|
| `BRIEF.md` | What to build | Agent writes from the user's idea |
| `STANDARDS.md` | Shared philosophy, stack, security and UI rules | Never per project; improve it in the boilerplate repo instead |
| `COST_CAUTIONS.md` | **Mandatory.** Runaway-cost rules (fixed) + this project's limits and worst case (agent fills) | Never delete |
| `AGENTS.md` | Project rules for coding agents; read by Codex automatically | Agent fills, then grows with the project |
| `CLAUDE.md` | Makes Claude Code load AGENTS.md, STANDARDS.md and COST_CAUTIONS.md | No |
| `README.md` | Project readme | Agent fills |
| `HOSTING.md` | Links, one-time setup, deploy, local | Agent fills when hosting starts |
