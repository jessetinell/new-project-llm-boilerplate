# Start here

Markdown-only boilerplate for new projects. Delete this file once the project is set up.

## For the human: one prompt

Open `claude` or `codex` in an **empty folder** and paste:

> Bootstrap this folder from the boilerplate at `github.com/<github-user>/boilerplate` and follow its START_HERE.md. My idea: <describe the app: what, for whom, must-haves, anything you already know>

Before it's on GitHub, give a local path instead: `…from the boilerplate at ~/<path-to>/boilerplate…`

That's it. The agent copies the files, writes the brief from your idea, asks only what's blocking, and sets up the project.

## For the agent: setup steps

1. **Copy the boilerplate** into the current (empty) folder without its git history:
   - GitHub: `gh repo clone <github-user>/boilerplate . -- --depth 1 && rm -rf .git && git init`
   - Local path: `cp -R <path>/. . && rm -rf .git && git init`
2. **Read** `STANDARDS.md` and `COST_CAUTIONS.md` fully.
3. **Write `BRIEF.md`** from the user's idea. Keep their words; leave unknown sections out rather than guessing.
4. **Ask only what's blocking** (at most a few questions, in one go). Use the defaults in `STANDARDS.md` for everything else.
5. **Fill the placeholders** (`{{…}}`) in `AGENTS.md`, `README.md`, `HOSTING.md` and the project section of `COST_CAUTIONS.md`. Delete `API.md` if there's no API. Never delete `COST_CAUTIONS.md`.
6. **Scaffold the app** with the default stack (or the user's override), smallest working version first.
7. **Check:** `grep -rn "{{" *.md` returns nothing; the app runs locally.
8. **Delete this file.** Then summarize what was set up, what's next, and anything the human must do in a dashboard (list it in `HOSTING.md`).

Never deploy or change anything live without asking.

## What's here

| File | Purpose | Edit? |
|---|---|---|
| `BRIEF.md` | What to build | Agent writes from the user's idea |
| `STANDARDS.md` | Shared philosophy, stack, security and UI rules | Never per project; improve it in the boilerplate repo |
| `COST_CAUTIONS.md` | **Mandatory.** Runaway-cost rules (fixed) + this project's limits and worst case (agent fills) | Never delete |
| `AGENTS.md` | Project rules for coding agents; read by Codex automatically | Agent fills, then grows with the project |
| `CLAUDE.md` | Makes Claude Code load AGENTS.md, STANDARDS.md and COST_CAUTIONS.md | No |
| `README.md` | Project readme | Agent fills |
| `HOSTING.md` | Links, one-time setup, deploy, local | Agent fills when hosting starts |
| `API.md` | API reference | Only if there's an API |
