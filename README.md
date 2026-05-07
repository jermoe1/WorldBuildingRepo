# [World Name] — Worldbuilding Repository

> Master repository for all lore, worldbuilding content, and session records.
> This repo is maintained in parallel with a Claude AI worldbuilding project.
> `CLAUDE.md` in this repo contains the WorldBuildingAssistant behavior file — personas, commands, and the Auxiliary File Registry.
> **This repo is the source of truth for all lore content.**

---

## Repository Structure

```
/
├── README.md                   ← This file
├── CLAUDE.md                   ← WorldBuildingAssistant behavior file (personas, commands, registry)
├── CHANGELOG.md                ← Session-by-session record of what changed and when [NOT YET CREATED]
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
                                   [sessions/2026-05-07.md not yet exported]
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
| Geography.md | Partial | 2026-05-07 |
| Factions.md | Partial | 2026-04-26 |
| MagicSystem.md | Scaffold only | 2026-04-26 |
| Peoples.md | Scaffold only | 2026-04-26 |
| Timeline.md | Partial | 2026-04-26 |
| NamingConventions.md | Partial | 2026-05-07 |
| Relationships.md | Scaffold only | 2026-04-26 |
| NPCs.md | Partial | 2026-05-07 |
| Artifacts.md | Partial | 2026-05-07 |
| GameMechanics.md | Sparse | 2026-04-26 |
| RawImports.md | Scaffold only | 2026-04-26 |

> Update this table whenever a file receives substantive content.

---

## Canon Registry

> As of v1.9.0 (2026-05-07), the Canon Registry was extracted from CLAUDE.md into a dedicated `CanonRegistry.md` file maintained in Claude project knowledge. It is no longer mirrored here.
> Current count: **40 confirmed entries** (as of session 2026-05-07).
> To review or update canon, use `Run canon:` in a Claude session.

---

*Genre: Dark Fantasy / Grimdark — System: Homebrew / System-Agnostic*
