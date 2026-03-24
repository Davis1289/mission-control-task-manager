# Contributing to Launchpad

This repo uses a **branch-per-tool** workflow. Each AI tool has its own dedicated branch. Changes are reviewed and merged into `main` by the repo owner.

---

## Branch Map

| Branch | Tool | Purpose |
|--------|------|---------|
| `main` | — | Stable, always working. Never commit directly here. |
| `claude-code` | Claude Code (CLI) | Terminal-based agentic coding sessions |
| `cursor-ai` | Cursor AI | IDE-based AI completions and Composer sessions |
| `openclaw` | OpenClaw agents | Autonomous agent task execution |

---

## Workflow for Each Tool

### Claude Code → `claude-code` branch

```bash
# Clone and switch to your branch
git clone https://github.com/Davis1289/mission-control-task-manager
cd mission-control-task-manager
git checkout claude-code

# Start a session
claude

# Inside Claude Code, say:
# "Read AGENTS.md, pick the next unchecked High Priority item from BACKLOG.md, implement it in launchpad.html"

# When done, push
git push origin claude-code
```

Then open a Pull Request: `claude-code` → `main` on GitHub for review.

---

### Cursor AI → `cursor-ai` branch

```bash
git checkout cursor-ai
# Open the folder in Cursor
```

In Cursor Composer, use this prompt:
```
Read AGENTS.md to understand the codebase rules.
Then read BACKLOG.md and pick the next unchecked item.
Implement it in launchpad.html only — no new files, no dependencies.
Commit with format: feat: <description>
```

Push and open a PR: `cursor-ai` → `main`.

---

### OpenClaw → `openclaw` branch

System prompt for your OpenClaw agent:
```
You are working on GitHub repo Davis1289/mission-control-task-manager, branch: openclaw.

Step 1: Read AGENTS.md — understand the architecture and follow all 7 rules.
Step 2: Read BACKLOG.md — pick the first unchecked High Priority item.
Step 3: Implement it in launchpad.html only. No new files. No dependencies.
Step 4: Commit with message: feat: <description>
Step 5: Mark the completed item as done in BACKLOG.md in a second commit.
Step 6: Open a Pull Request from openclaw into main.
```

---

## Pull Request Rules

1. **One backlog item per PR** — never bundle multiple features
2. **Title format:** `feat: <backlog item name>` or `fix: <what was fixed>`
3. **Test before pushing:** Open `launchpad.html` in Chrome, open DevTools console, confirm zero errors
4. **Update BACKLOG.md:** Mark the completed item with `[x]` in the same PR or a follow-up commit

---

## Merging

Only the repo owner (@Davis1289) merges PRs into `main`. After merging, GitHub Pages auto-updates within ~60 seconds.

---

## Branch Sync

Keep your working branch up to date with main before starting a new task:

```bash
git checkout claude-code   # or cursor-ai / openclaw
git pull origin main
git push origin claude-code
```

---

## Questions

If you're an AI agent and something is unclear, check `AGENTS.md` first. That file is the source of truth for all architecture and style decisions.
