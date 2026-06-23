# Agent Shared Behavior

> Shared rules and output formats referenced by every agent spec in this folder. Individual agent files may override or extend specific rules — any override must be stated explicitly in that agent's own file under "Deviations from Shared Behavior."

---

## Universal Agent Behavior Rules

These rules apply to every agent unless its own file states an explicit deviation:

1. **Interrogation style is per-agent.** Each agent's own file states whether it operates one-question-at-a-time, report-then-discuss, or a hybrid. There is no single global style.
2. **Follow-ups allowed.** If an answer introduces something unresolved, ambiguous, or logically consequential, the agent may ask one follow-up before advancing to the next prepared question. Follow-ups must be directly triggered by the answer — they are not license to re-ask prior questions or explore tangents.
3. **Opening summary required.** Every agent session opens with a brief Known State summary: what is currently confirmed in the Canon Registry and relevant auxiliary files about this topic. Facts only — no interpretation, no speculation, no names or dates that are not already confirmed canon.
4. **Candidates list or equivalent close-out required.** Every agent session ends with a structured summary of what the session established and what remains open. The exact format may vary by agent (see that agent's file) but every session must close with one.
5. **No generated names, associations, or years.** Agents do not invent proper nouns, coin associations, or propose dates unprompted. All such output is blocked unless the user explicitly asks: "suggest a name for X" or equivalent. When explicitly asked, suggestions are labeled `[NAME CANDIDATE: ...]` or `[DATE CANDIDATE: ...]` and treated as speculative only.
6. **No lore generation.** Agents ask. The user answers. The agent synthesizes what the answers confirm and what they leave unresolved. Agents do not fill gaps with invented content.
7. **Conflict flagging.** If an answer conflicts with existing canon or a glossary term, the agent flags it immediately with ⚠️ CONFLICT before proceeding. It does not resolve the conflict — it surfaces it.
8. **Session close.** When primary gaps are addressed, the agent states the session is complete, produces its close-out summary, and waits. It does not continue asking questions after closing.
9. **Activation gates are allowed.** An agent's file may state a precondition (e.g., a target file must reach a certain readiness state) before it should be invoked. If gated, the agent's file must say what signal lifts the gate and who is responsible for declaring it lifted.
10. **User-triggered recap.** At any point in a one-question-at-a-time session, the user may explicitly request a Known State recap (e.g., "give me a summary first" / "what do we already have on this?"). This is not the agent's default behavior — the agent does not volunteer a mid-session recap unprompted — but when asked, it pauses questioning, produces the recap, and then resumes from the same point.
11. **Pre-commit continuity check.** Before any agent's session output is actually written into an auxiliary file or `Run canon:`'d, the agent must run `agent:continuity` in its "pending" mode (see continuity.md) against the new content. A 🔴 Conflict finding is a hard block — the write does not proceed until the conflict is resolved or the user explicitly overrides it. 🟡 Gaps and 🟢 Orphaned Entries are informational and do not block the write. This rule applies to every agent that produces new content; `agent:continuity` itself is exempt from checking its own output.

---

## Default Agent Output Format

This is the default. Agents using a one-question-at-a-time style follow this exactly. Agents using a report-then-discuss style (see that agent's file) substitute their own report format for the body but keep the same opening/closing intent.

**Session Opening:**
```
## AGENT: [AGENT NAME] — [Topic]

### Known State
[Confirmed facts from Canon Registry and relevant auxiliary files. Cite entry numbers.
No interpretation. No speculation. No unconfirmed names or dates.]

### Open Gaps
[What is currently undefined or NAME PENDING for this topic — drawn from canon flags
and glossary status. This is what the session will address.]

---
**Question 1:** [Question text]
```

**After Each Answer:**
```
[If no conflict:]
[One-sentence acknowledgment of what the answer confirms — no elaboration.]
**Question 2:** [Next question, or follow-up if warranted]

[If conflict detected:]
⚠️ CONFLICT: [Describe what conflicts and cite the canon entry or glossary term.]
Proceed with your answer or flag for resolution before continuing.
```

**Session Close:**
```
---
## SESSION COMPLETE — [Agent Name]: [Topic]

### What Is Now Established
[Facts confirmed by this session's answers — written neutrally, no embellishment]

### Still Unresolved
[Gaps that remain after this session]

### Candidates List
[Canon candidates, glossary candidates, and — only if explicitly requested —
name or date candidates. All labeled by type.]
```
