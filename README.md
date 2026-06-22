# [World Name] — Worldbuilding Repository

> Master repository for all lore, worldbuilding content, and session records.
> This repo is maintained in parallel with a Claude AI worldbuilding project.
> `meta/CLAUDE.md` in this repo contains the WorldBuildingAssistant behavior file — agent architecture, commands, and the Auxiliary File Registry.
> **This repo is the source of truth for all lore content.**

---

## Repository Structure

> Restructured in v2.0.0 (2026-06-22). Folders are organized by content layer rather than a flat core/optional split.

```
/
├── README.md                   ← This file
├── CHANGELOG.md                ← Session-by-session record of what changed and when
├── CanonRegistry.md            ← Confirmed canon facts (40 entries)
├── Glossary.md                 ← Proper nouns and terminology index
├── ConflictTracker.md          ← Open/resolved lore contradictions
├── ToDoList.md / RawIdeas.md / SessionLog.md / InWorldDocuments.md
│
├── meta/                       ← Behavior layer and naming/relationship reference
│   ├── CLAUDE.md               ← WorldBuildingAssistant behavior file (agent architecture, commands, registry)
│   ├── NamingConventions.md
│   ├── Relationships.md
│   └── RawImports.md
│
├── foundation/                 ← Cosmological and magical bedrock
│   ├── Cosmology.md            ← Pre-pantheon genealogical tree, Genesis Era mechanics
│   ├── MagicSystem.md
│   └── Planes.md
│
├── history/                    ← Chronology
│   ├── Timeline.md             ← Calendar, dating system, master spine
│   ├── Eras.md                 ← One entry per era
│   └── Events.md                ← Named historical events
│
├── world/                       ← Physical world
│   ├── Geography.md
│   ├── Geology.md              ← Scaffold — populated during Physical World phase
│   └── Peoples.md
│
├── powers/                      ← Who holds power
│   ├── Gods.md
│   ├── Factions.md
│   └── NPCs.md
│
├── systems/                     ← Mechanics and objects
│   ├── Artifacts.md
│   └── GameMechanics.md
│
├── campaign/                    ← Campaign-ready material
│   ├── Premise.md
│   ├── Arcs.md
│   └── Sessions/
│
├── sessions/                    ← Full session logs, one file per session
│   └── YYYY-MM-DD.md           ← Named by session date
│
└── tmp/                          ← Raw, unprocessed import source material
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
| foundation/Cosmology.md | Scaffold | 2026-06-22 |
| foundation/MagicSystem.md | Scaffold only | 2026-04-26 |
| foundation/Planes.md | Sparse | 2026-06-22 |
| history/Timeline.md | Partial | 2026-06-22 |
| history/Eras.md | Sparse | 2026-06-22 |
| history/Events.md | Sparse | 2026-06-22 |
| world/Geography.md | Partial | 2026-05-07 |
| world/Geology.md | Scaffold only | 2026-06-22 |
| world/Peoples.md | Scaffold only | 2026-04-26 |
| meta/NamingConventions.md | Partial | 2026-05-07 |
| meta/Relationships.md | Scaffold only | 2026-04-26 |
| meta/RawImports.md | Scaffold only | 2026-04-26 |
| powers/Gods.md | Scaffold only | 2026-04-26 |
| powers/Factions.md | Partial | 2026-04-26 |
| powers/NPCs.md | Partial | 2026-05-07 |
| systems/Artifacts.md | Partial | 2026-05-07 |
| systems/GameMechanics.md | Sparse | 2026-04-26 |
| campaign/Premise.md | Scaffold only | 2026-06-22 |
| campaign/Arcs.md | Scaffold only | 2026-06-22 |

> Update this table whenever a file receives substantive content.

---

## Canon Registry

> As of v1.9.0 (2026-05-07), the Canon Registry was extracted from CLAUDE.md into a dedicated `CanonRegistry.md` file maintained in Claude project knowledge. It is no longer mirrored here.
> Current count: **40 confirmed entries** (as of session 2026-05-07).
> To review or update canon, use `Run canon:` in a Claude session.

---

*Genre: Dark Fantasy / Grimdark — System: D&D 5e (primary), system-agnostic where possible*
