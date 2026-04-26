# [World Name] — Worldbuilding Repository

> Master repository for all lore, worldbuilding content, and session records.
> This repo is maintained in parallel with a Claude AI worldbuilding project.
> The Claude project's `WorldBuildingAssistant.md` governs behavior, personas, and commands — it lives in Claude Project Knowledge, not here.
> **This repo is the source of truth for all lore content.**

---

## Repository Structure

```
/
├── README.md                   ← This file
├── CHANGELOG.md                ← Session-by-session record of what changed and when
│
├── lore/                       ← All worldbuilding content
│   ├── core/                   ← Must-have files — establish these first
│   │   ├── Gods.md
│   │   ├── Geography.md
│   │   ├── Factions.md
│   │   ├── MagicSystem.md
│   │   ├── Peoples.md
│   │   ├── Timeline.md
│   │   ├── NamingConventions.md
│   │   └── Relationships.md
│   │
│   └── optional/               ← Created as needed
│       ├── NPCs.md
│       ├── Artifacts.md
│       ├── GameMechanics.md
│       └── RawImports.md
│
└── sessions/                   ← Full session logs, one file per session
    └── YYYY-MM-DD.md           ← Named by session date
```

---

## Workflow

### During a session (Claude app)
- Work happens in the Claude worldbuilding project
- All personas, commands, and lore development happen there

### After a session (desktop)
1. Open the Claude conversation
2. Locate the `/log` export packet at the end of the session
3. For each modified file listed in the packet:
   - Copy the file content from the export
   - Overwrite the corresponding file in this repo
4. Copy the session log entry into `sessions/YYYY-MM-DD.md`
5. Update `CHANGELOG.md` with a one-line summary
6. Commit with the message format: `Session YYYY-MM-DD — [brief description]`

### Commit message format
```
Session YYYY-MM-DD — [one sentence describing the session's focus]
```
Example: `Session 2026-04-26 — Initial scaffold, repo structure established`

---

## File Status

| File | Status | Last Updated |
|---|---|---|
| Gods.md | Scaffold only | 2026-04-26 |
| Geography.md | Scaffold only | 2026-04-26 |
| Factions.md | Scaffold only | 2026-04-26 |
| MagicSystem.md | Scaffold only | 2026-04-26 |
| Peoples.md | Scaffold only | 2026-04-26 |
| Timeline.md | Scaffold only | 2026-04-26 |
| NamingConventions.md | Scaffold only | 2026-04-26 |
| Relationships.md | Scaffold only | 2026-04-26 |
| NPCs.md | Scaffold only | 2026-04-26 |
| Artifacts.md | Scaffold only | 2026-04-26 |
| GameMechanics.md | Scaffold only | 2026-04-26 |
| RawImports.md | Scaffold only | 2026-04-26 |

> Update this table whenever a file receives substantive content.

---

## Canon Registry

> Mirrors the Canon Registry in WorldBuildingAssistant.md. Update after every session where canon is confirmed.

| # | Confirmed Fact | Session | Date Added |
|---|---|---|---|
| — | *(None yet)* | — | — |

---

*Genre: Dark Fantasy / Grimdark — System: Homebrew / System-Agnostic*
