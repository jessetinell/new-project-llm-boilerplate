# Boilerplate

Markdown-only starting point for new projects: standards, cost safety, and doc templates for Claude Code and Codex. No code.

## Start a new project

Open `claude` or `codex` in an **empty folder** and paste:

> Bootstrap this folder from `github.com/<github-user>/boilerplate`: copy the contents of its `template/` folder here (not the repo root), then follow `START_HERE.md`. My idea: <what, for whom, must-haves, anything you already know>

Before it's on GitHub, give a local path instead: `…from ~/<path-to>/boilerplate: copy the contents of its template/ folder here…`

The agent copies `template/`, writes the brief from your idea, asks only what's blocking, and gets the project running locally. When you're ready, say **deploy it**: the agent sets up hosting, deploys, and fills in `docs/HOSTING.md`.

Copy command (for the agent, or by hand):

```sh
tmp=$(mktemp -d) && gh repo clone <github-user>/boilerplate "$tmp" -- --depth 1 && cp -R "$tmp/template/." . && rm -rf "$tmp" && git init
```

## Layout

| Path | What | Copied into projects? |
|---|---|---|
| `template/` | The boilerplate itself | **Yes**, its contents |
| `README.md` | This file: how to use the repo | No |
| `AGENTS.md`, `CLAUDE.md` | Guide for agents improving this repo | No |

## Improve it

Open `claude` or `codex` in this repo and describe the improvement (e.g. a lesson from a real project). `AGENTS.md` tells the agent how to work here.
