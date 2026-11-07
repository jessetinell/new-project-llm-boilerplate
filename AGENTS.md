# Boilerplate repo: maintainer guide

You are working **on the boilerplate itself**, not on a project made from it.

## What this repo is

- `template/`: the boilerplate. Its **contents** are copied into new, empty project folders, where agents bootstrap a real project by following `template/START_HERE.md`.
- Root files (`README.md`, this file, `CLAUDE.md`): about this repo. They are **never copied**.

Don't mix the two: `template/AGENTS.md` and `template/CLAUDE.md` belong to future projects and have nothing to do with this file.

## Files in `template/`

| File | Role in a new project |
|---|---|
| `START_HERE.md` | Bootstrap playbook for the agent; deleted once the project is set up |
| `BRIEF.md` | What to build; the agent writes it from the user's idea |
| `STANDARDS.md` | Shared philosophy, stack, auth, UI and docs rules; identical in every project |
| `COST_CAUTIONS.md` | Mandatory runaway-cost rules (fixed part) + project limits (placeholder part); never deleted |
| `AGENTS.md`, `CLAUDE.md` | The project's agent guide; `CLAUDE.md` loads AGENTS, STANDARDS and COST_CAUTIONS |
| `README.md`, `HOSTING.md` | Templates the agent fills |

## Rules for changes

- **Markdown only.** No code, scripts or config in this repo beyond `.gitattributes` and `.gitignore` (shell one-liners inside docs are fine).
- **Everything in `template/` stays generic:** no project names, URLs, IDs or account details. Use `{{placeholders}}` for anything project-specific.
- **Never weaken** the cost-safety or security rules. Add to them, clarify them, keep them brief.
- **Brief beats complete.** Every line must change what an agent does; cut anything that doesn't.
- **Keep the flow in sync:** the bootstrap prompt and copy command in `README.md`, and the steps in `template/START_HERE.md`, must agree.
- **The philosophy applies here too:** read `template/STANDARDS.md` before editing.
- **Ignore `.DS_Store`** anywhere in this repo: never read, edit, commit or mention it.
- **Where improvements come from:** lessons from real projects. Generalize them (strip specifics), then put each in the one file it belongs to; don't repeat a rule across files.

## Check a change

1. Bootstrap into a scratch folder: `d=$(mktemp -d) && cp -R template/. "$d" && ls "$d"`. You should see only template files.
2. Read `template/START_HERE.md` as a fresh agent would, with no other context: can it set up a project from just a one-line idea?
3. `grep -rn "{{" template/` shows only intended placeholders.
