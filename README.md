# Launchpad — Mission Control for Solo Developers

A single-file HTML project management dashboard built around the **FORGE Method** — a personal system for solo developers who have too many half-finished projects and not enough shipped things.

**No install. No server. No dependencies. Just open `launchpad.html` in Chrome.**

---

## Features

- **Active Mission** — Pin one project to the header as today's focus. Everything else waits.
- **Project cards** — Status badges, priority dots, and a staleness indicator (flags projects untouched 14+ days)
- **Context snapshots** — A "where I left off" field per project so you never lose your place
- **Next step** — One concrete 30–60 min action always defined per project
- **AI Advisor** — Powered by Claude. Get priority rankings, concrete next steps, and improvement suggestions
- **Parking Lot** — Capture ideas instantly without derailing your current work; promote any idea to a project when ready
- **Import projects** three ways:
  - Folder scan — Pick your coding projects folder; auto-detects projects from `package.json`, `README.md`, `.git`, and file types
  - CSV / JSON — Upload a spreadsheet of your projects (templates included)
  - GitHub API — Pull all your repos and import as projects with one click
- **Persistent storage** — Data saves automatically across sessions

---

## The FORGE Method

| Letter | Rule |
|--------|------|
| **F** | **Focus** — One project owns the day |
| **O** | **One next step** — Always defined, always specific |
| **R** | **Record context** — Update "where I left off" before every close |
| **G** | **Gate new ideas** — Park them, don't chase them |
| **E** | **Evaluate weekly** — Commit or cut every stalled project |

Click **"The FORGE Method"** in the toolbar to read the full breakdown.

---

## Getting Started

1. Download `launchpad.html`
2. Open it in **Chrome or Edge**
3. Click **⇑ Import** to pull in your existing projects
4. Set your **Active Mission** for today
5. Use the **AI Advisor** to get your first next step

---

## Tech Stack

- Pure HTML / CSS / JavaScript — zero dependencies, zero build step
- Anthropic Claude API for AI Advisor features
- File System Access API for folder scanning (Chrome/Edge only)
- GitHub REST API for repo import
- `window.storage` for persistent data

---

## AI Agent Contributions

This repo is set up for AI agents (Claude Code, Cursor, etc.) to contribute improvements autonomously.

- **`AGENTS.md`** — Rules and architecture guide for any agent working on this repo
- **`BACKLOG.md`** — Prioritized feature list agents can pull tasks from

If you're an agent: read `AGENTS.md` first, pick one item from `BACKLOG.md`, implement it in `launchpad.html`, and commit.

---

Built by [@Davis1289](https://github.com/Davis1289)
