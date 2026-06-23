# Phone Capture Workflow

> How a raw idea typed into the "Worldbuilding" Claude Project on a phone gets from that chat into this repo. This process is deliberately separate from the desktop agent architecture in `CLAUDE.md` — a phone session has no repo access, no file write ability, and may be working from stale Project Knowledge. Its only job is fast, clean capture. All classification, interrogation, and canon-checking happens later, at a desktop session with full repo context.

---

## One-Time Setup

1. Open the "Worldbuilding" Claude Project → Settings → Custom Instructions.
2. Paste in the contents of [`meta/ProjectCustomInstructions.md`](ProjectCustomInstructions.md) exactly as written.
3. Load a starter set of Project Knowledge files (desktop client only — see [Project Knowledge Refresh](#project-knowledge-refresh) below for which files and how to keep them current).

This setup only needs to happen once, and again any time `meta/ProjectCustomInstructions.md` changes.

---

## During a Phone Session

1. Open the "Worldbuilding" Project on the Claude Android app.
2. Type the idea — a fragment, a question, a name, a half-formed concept. No need to structure it.
3. The Project's custom instructions handle the rest: light cleanup, one category tag, at most one clarifying question if genuinely needed, and a closing **Capture Block**.
4. If you have multiple unrelated ideas in one session, let each one close out with its own Capture Block rather than mixing them — keeps desktop triage clean.
5. Leave the chat as-is. Nothing needs to happen on the phone beyond this. Don't try to get the phone session to classify against canon, resolve naming, or develop the idea further — that's what desktop sessions and `Run develop:` are for.

---

## Desktop Handoff

Do this next time you're at a desktop with repo access — no urgency, batch as many sessions as you want:

1. Open the phone chat(s) and copy each Capture Block.
2. Paste each one into `RawIdeas.md`, under the **📱 Phone Captures — Unprocessed** section (added above the general sections so they stay visible until triaged).
3. Once pasted, the idea is in the normal pipeline: triage it like any `RawIdeas.md` entry — either leave it for later, or run it through `Run develop:` (see `CLAUDE.md` § Develop Protocol) when ready to flesh it out.
4. After an idea is triaged out of the Phone Captures section (moved to an agent session, promoted to canon, or discarded), remove it from that section the same way `Run develop:` already retires `RawIdeas.md` entries — leave a one-line cross-reference to where it went, don't delete silently.

---

## Project Knowledge Refresh

Project Knowledge on the phone is a **static snapshot** — it does not auto-update when the repo changes, and the GitHub file-picker that makes refreshing easy only exists on the desktop client (not the Android app). So refreshing is a desktop-only, manual, occasional action.

**When to refresh:** after a merge to `main` that changes `CanonRegistry.md`, `Glossary.md`, or any populated lore file — not after every commit. Tracking/process churn (ToDo, SessionLog, ConflictTracker) doesn't warrant a refresh.

**What to load** (desktop client → Worldbuilding Project → Add File → GitHub):
- `CLAUDE.md` (only if it changed — phone sessions don't need the full behavior layer, but it doesn't hurt as background context)
- `CanonRegistry.md`
- `Glossary.md`
- Any populated file under `foundation/`, `history/`, `world/`, `powers/`, `systems/`, `campaign/` that's past "Scaffold" status

**What to skip:** `ToDoList.md`, `SessionLog.md`, `ConflictTracker.md`, `RawIdeas.md`, `meta/RawImports.md`, `tmp/`, anything under `sessions/` or `campaign/Sessions/`. These are tracking/process files a phone capture session has no use for, and they add noise that crowds out the lore content that actually matters for a quick "does this fit what's already established" gut-check.

Re-picking a file in the GitHub picker replaces the stale copy — it does not duplicate it, but double-check the Project Knowledge list afterward if you're unsure.

---

*— meta/PhoneCapture.md — Cross-reference: `meta/ProjectCustomInstructions.md`, `CLAUDE.md` § Develop Protocol, `RawIdeas.md` § Phone Captures —*
