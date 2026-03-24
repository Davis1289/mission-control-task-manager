# Launchpad — Agent Backlog

Agents: pick ONE unchecked item, implement it in `launchpad.html`, commit with a descriptive message, and mark it as done here in a follow-up commit. Read AGENTS.md first — always.

---

## 🔴 High Priority

- [ ] **Export backup** — Add an "Export JSON" button to the toolbar that downloads all projects + ideas as a timestamped `.json` file. Use `JSON.stringify(S)` and a Blob download.
- [ ] **Weekly Review mode** — A modal that loops through every Stalled project one at a time and forces a binary decision: "Recommit (set next step)" or "Archive". Projects marked Archive get status set to `archived` and are hidden from default view.
- [ ] **Session log per project** — Each project gets a collapsible log of timestamped notes. When you update "Where I Left Off", the old value is appended to the log with a timestamp instead of being overwritten.

---

## 🟡 Medium Priority

- [ ] **Keyboard shortcuts** — `N` opens new project modal, `F` focuses the idea input, `/` opens search. Show a shortcut cheatsheet on `?` key.
- [ ] **Search + filter bar** — A text input in the toolbar that filters project cards in real time by name, description, category, or tags.
- [ ] **Project tags** — Allow multiple comma-separated tags per project. Tags are filterable from the toolbar. Store as an array on the project object.
- [ ] **Streak tracker** — Display a fire emoji + count on cards touched on consecutive days. Store a `touchDates` array per project and compute streak on render.
- [ ] **Archived status** — Add `archived` as a sixth status. Archived projects don't show by default. Add a toggle in the toolbar to show/hide archived.
- [ ] **Drag to reorder** — Allow manual drag-and-drop reordering of project cards within the current filter view. Persist order in state.

---

## 🟢 Polish / Nice to Have

- [ ] **Confetti on release** — When a project status is cycled to `released`, trigger a small canvas confetti burst for 1.5 seconds.
- [ ] **Mobile layout** — On viewports under 768px, the sidebar stacks below the project grid instead of being a fixed column.
- [ ] **Stale AI nudge** — For any project untouched for 14+ days, the AI Advisor automatically suggests a next step when the card is clicked.
- [ ] **README sync** — Add a "Copy status report" button that generates a markdown summary of all active projects, ready to paste into a README or standup note.
- [ ] **Color-coded categories** — Assign a consistent hue to each unique category tag. Cards with the same category share a subtle left-border tint.
- [ ] **Project completion %** — Add an optional `progress` field (0–100). Display as a thin progress bar at the bottom of the card.

---

## ✅ Completed

- [x] Initial single-file app with project cards, status, priority, focus mission
- [x] AI Advisor sidebar (priority, next steps, improvements)
- [x] Parking Lot idea capture + promote-to-project
- [x] Import: folder scan, CSV/JSON file upload, GitHub API
- [x] Persistent storage via window.storage
- [x] FORGE Method modal
- [x] AGENTS.md + BACKLOG.md agent infrastructure
