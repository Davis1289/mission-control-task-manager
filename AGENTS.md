# AGENTS.md — AI Agent Instructions for Launchpad

This file is the primary instruction set for any AI agent (OpenClaw, Claude Code, Cursor, etc.) working on this repository. Read this before making any changes.

---

## What This Project Is

**Launchpad** is a single-file HTML project management dashboard for solo developers. It helps track projects, maintain focus, capture ideas, and get AI-powered recommendations.

- **One file only:** `launchpad.html` — all HTML, CSS, and JavaScript lives here
- **No build step, no dependencies, no npm** — pure vanilla HTML/CSS/JS
- **Persistent storage:** Uses `window.storage` API (Claude artifact storage) for data persistence
- **AI integration:** Calls `https://api.anthropic.com/v1/messages` using `claude-sonnet-4-20250514`

---

## Architecture

```
launchpad.html
├── <style>          CSS variables + all styles (no external CSS)
├── <body>           Header, toolbar, main grid, sidebar, modals
└── <script>
    ├── STATE        S = { projects[], ideas[], focusId }
        ├── STORAGE      load() / save() via window.storage
            ├── RENDER       render(), renderHeader(), renderGrid(), renderIdeas()
                ├── ACTIONS      setFocus, cycleStatus, deleteProject, addIdea, promoteIdea
                    ├── MODALS       Project modal, Import modal (folder/file/github), FORGE modal
                        ├── IMPORT       doFolderScan(), doGitHub(), handleFileImport(), doImport()
                            └── AI ADVISOR   ai('priority' | 'nextstep' | 'improve') → Anthropic API
                            ```

                            ### Key Data Shape
                            ```js
                            project = {
                              id: string,           // uid()
                                name: string,
                                  description: string,
                                    status: 'idea' | 'building' | 'stalled' | 'polish' | 'released',
                                      priority: 1-5,
                                        category: string,
                                          context: string,      // "where I left off"
                                            nextStep: string,
                                              lastUpdated: ISO string,
                                                createdAt: ISO string,
                                                }
                                                ```

                                                ---

                                                ## Agent Rules

                                                1. **Never split into multiple files.** Everything stays in `launchpad.html`. No external JS, no external CSS, no frameworks.
                                                2. **Preserve the storage API.** All reads/writes use `window.storage.get/set`. Do not introduce localStorage or sessionStorage.
                                                3. **Preserve the Anthropic API call.** Model must stay `claude-sonnet-4-20250514`. Max tokens stays 1000.
                                                4. **Keep CSS variables.** All colors reference `:root` CSS variables — never hardcode hex values inline.
                                                5. **Match the visual style.** Dark theme, teal accent (`#00d4b4`), IBM Plex Mono + Syne fonts. Do not introduce new font families.
                                                6. **Test for regression.** After any change, verify: add project, edit project, cycle status, set focus, add idea, promote idea, all three import tabs open correctly, AI advisor buttons fire without console errors.
                                                7. **Commit messages** should follow: `feat: ...`, `fix: ...`, `chore: ...`, `refactor: ...`

                                                ---

                                                ## Current Features

                                                - Project cards with status, priority dots, staleness indicator
                                                - Active Mission pinned to header
                                                - Status cycling (idea → building → stalled → polish → released)
                                                - Context snapshot ("where I left off") per project
                                                - Next step per project
                                                - AI Advisor: priority ranking, next steps, improvement suggestions
                                                - Parking Lot idea capture with promote-to-project
                                                - Import: folder scan (File System Access API), CSV/JSON file, GitHub API
                                                - Persistent storage across sessions

                                                ---

                                                ## Backlog (see BACKLOG.md)

                                                Pull your next task from `BACKLOG.md`. Pick one item, implement it in `launchpad.html`, and submit a PR. Do not work on multiple backlog items in a single PR.

                                                ---

                                                ## How to Test

                                                Open `launchpad.html` directly in Chrome or Edge. No server needed. Open DevTools console and confirm zero errors on load and after interactions.

                                                ---

                                                ## Owner

                                                Built by Davis1289. Agent contributions welcome — follow the rules above.
