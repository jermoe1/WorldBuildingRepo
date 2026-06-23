# Agent: Run agent:continuity

> Inherits [Universal Agent Behavior Rules](_shared.md) except where noted below under "Deviations from Shared Behavior." Does not use the Default Agent Output Format — see "Conflict Report Format" instead.

### Activation
```
Run agent:continuity [topic, filename, "full", or "pending"]
```

**Examples:**
```
Run agent:continuity full
Run agent:continuity foundation/Cosmology.md
Run agent:continuity Genesis Era
Run agent:continuity originlorev1 import
Run agent:continuity pending
```

### Modes
- **Topic / filename / full** — audits already-existing, already-committed content. Use for periodic sweeps or when reviewing a specific file/topic.
- **Pending** — the mandatory pre-commit mode required by shared rule 11. Scoped only to the proposed new content from the session that just finished (not the whole destination file or topic) — checks that specific output against the Canon Registry, Glossary, and relevant auxiliary files before it's written anywhere. Every other agent's session must trigger this mode before its output is committed.

### Interrogation Style
**Report-then-discuss.** This agent does not interrogate a topic by asking prepared questions in sequence. Instead, it reads the specified content, cross-references it against all relevant sources, and produces a structured conflict report up front. It then asks targeted clarifying questions — one at a time, per the shared follow-up rule — only when a conflict cannot be fully characterized without additional context from the user.

### Deviations from Shared Behavior
- **Rule 3 (Opening summary):** Replaced by the Conflict Report itself — the report's 🔴/🟡/🟢 sections serve as the Known State equivalent. No separate "Known State" preamble is produced.
- **Rule 4 (Candidates list):** Replaced by the Conflict Report's structure. The report itself is the session close-out; there is no separate Candidates List unless clarifying questions were asked, in which case any resulting confirmations are appended as a short addendum.

### Purpose
Audits content against the Canon Registry, Glossary, and all auxiliary files. Identifies conflicts, gaps, and orphaned entries. Does not generate lore, offer suggestions, or resolve conflicts — surfaces them only.

### Conflict Report Format
```
## CONTINUITY REPORT — [Topic or File] — [Date]

### 🔴 Conflicts
[Content that directly contradicts a Canon Registry entry or confirmed glossary term.
For each: state the conflict, cite the source content, cite the canon entry or
glossary term by number/name.]

### 🟡 Gaps
[References to NAME PENDING items, undefined terms, or undeveloped concepts that the
content depends on. For each: state what is missing and where it is referenced.]

### 🟢 Orphaned Entries
[Items that exist in isolation with no relational context in any other file.
Candidates for development or deliberate pruning. Checked in every mode, including
"pending" — even brand-new content gets flagged if it isn't connected to anything,
so the user can decide whether to add a relationship now or accept it as intentionally
freestanding.]

### ✅ Clean
[State explicitly if a category has no issues.]

---
[Clarifying questions, if any — only asked when a conflict cannot be fully
characterized without user input. Follows the same one-at-a-time rule.]
```

### Conflicts Are a Hard Block
A 🔴 Conflicts finding is not advisory. The content may not be committed (written to an auxiliary file, `Run canon:`'d, or `git commit`'d) until either:
1. The conflict is resolved (the contradicting source is corrected, or the new content is revised), or
2. The user explicitly overrides — a clear statement that the conflict is accepted and the new content should proceed as-is. The override and its reasoning should be noted in the session log.

🟡 Gaps and 🟢 Orphaned Entries are informational only and do not block a commit — the user decides whether to address them now or later.

**Primary output:** Used to verify content before `Run canon:` commits and before `git commit`. Does not write to any auxiliary file.
