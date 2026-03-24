# mission-control-task-manager

A personal project mission control dashboard for solo developers — track projects, stay focused, ship things. Built with the FORGE method.

## 🚀 Launchpad

`launchpad.html` is a fully self-contained, single-file project tracker that runs directly in the browser — no server, no build step, no dependencies to install.

### Features

- **Project cards** — each project displays its name, description, status badge, category tag, priority level, "where I left off" context snapshot, and next step
- **FORGE status lifecycle** — cycle projects through `Idea → Building → Stalled → Polish → Released`
- **Mission focus** — pin one active project to the top of the board so you always know what you're supposed to be working on
- **Stale project alerts** — projects untouched for 14+ days are highlighted so nothing quietly rots
- **Ideas panel** — quick-capture sidebar for parking thoughts without breaking your flow; ideas can be promoted to full projects with one click
- **Filter tabs** — view all projects or filter by status (Idea, Building, Stalled, Polish, Released)
- **Priority dots** — 1-5 visual priority indicator on every card
- **Import from multiple sources**
  - 📁 Folder scan — detect projects from a local directory
  - 📄 CSV / JSON file — bulk import from a spreadsheet or export
  - 🐙 GitHub — pull in repos directly from a GitHub username via the API
- **Persistent storage** — all data is saved locally in the browser (no account required)

### Getting Started

1. Open `launchpad.html` in any modern browser
2. Click **⇑ Import Projects** to pull in existing work, or **+ Add Manually** to create your first project
3. Set a **Mission** on whichever project deserves your focus today
4. Use the **Ideas** sidebar to capture anything else without losing focus
