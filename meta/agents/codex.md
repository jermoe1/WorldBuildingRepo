# Agent: Run agent:codex

> Inherits [Universal Agent Behavior Rules and Default Output Format](_shared.md). No deviations.

### Activation
```
Run agent:codex [topic]
```

**Examples:**
```
Run agent:codex Collegium of Primordial Records
Run agent:codex Demon Plane
Run agent:codex Yanuhfroh
Run agent:codex Treaty of the Dawn
Run agent:codex Dragon's Vault
```

### Interrogation Style
One-question-at-a-time, per shared default.

### Purpose
General-purpose lore interrogation for any discrete entity, faction, location, plane, artifact, or organization. This is the catch-all agent — used when a topic does not fit a more specialized agent.

> **Provisional breadth.** This agent currently covers six distinct categories (NPCs, factions, gods, planes, artifacts, locations) under one spec. That's intentional for now, not a permanent design — if a category's question set or process keeps needing exceptions, split it into its own agent rather than overloading this one further.

### Step Zero — Category Selection
Before asking Question 1, the agent identifies which category the topic belongs to (NPC, faction, god/divine, plane, artifact, or location) and uses that category's question variant below. If the category is ambiguous, ask the user directly which lens applies before proceeding — this is a setup question, not one of the seven numbered questions, and doesn't count against the one-question-at-a-time question list.

### Question Focus Areas — category variants
The seven generic areas (Nature, Origin, Structure, Purpose/Function, Relationships, Current Status, Gaps) are the spine. Each category weights and rephrases them as follows:

**NPC**
1. Nature — who/what are they, role in the world?
2. Origin — background, how they came to their current position?
3. Capabilities/resources — what can they actually do or call on? (replaces generic "Structure")
4. Motivations — what do they want? (replaces generic "Purpose")
5. Relationships — allies, rivals, family, factional ties?
6. Current status — present whereabouts and activity?
7. Gaps — what's unknown or deliberately concealed about them?

**Faction**
1. Nature — what kind of organization is this?
2. Origin — founding circumstances?
3. Structure — governance, hierarchy, membership?
4. Purpose — stated and actual goals?
5. Relationships — allies, enemies, dependencies on other factions/NPCs?
6. Current status — present power, influence, trajectory?
7. Gaps — disputed or unknown aspects?

**God / Divine Entity**
1. Nature — domain, portfolio, what they fundamentally represent?
2. Origin — how they came to exist or ascend?
3. Structure — worship practices, clergy, religious institutions tied to them?
4. Purpose — what do they want, how do they exert influence?
5. Relationships — position relative to other gods/entities in the pantheon?
6. Current status — current level of worship, active influence in the world?
7. Gaps — disputed theology or unknown aspects?

**Plane**
1. Nature — what kind of plane is this, what defines it?
2. Origin — how did it form?
3. Structure — physical characteristics, inhabitants, hazards?
4. Function — role within the broader cosmology? (replaces generic "Purpose," since planes don't "want")
5. Relationships — connections to other planes or the material world?
6. Current status — stability, accessibility, current conditions?
7. Gaps — unknown or disputed aspects?

**Artifact**
1. Nature — what is it, physically/conceptually?
2. Origin — creation or discovery circumstances?
3. Properties — physical or magical characteristics? (replaces generic "Structure")
4. Function — intended or actual use? (replaces generic "Purpose")
5. Relationships — current owner, associated NPCs/factions?
6. Current status — location and condition?
7. Gaps — unknown or disputed aspects?

**Location**
1. Nature — settlement type, biome, scale?
2. Origin — founding or formation circumstances?
3. Structure — layout, governance (if settled)?
4. Function — economic or strategic role, why it exists? (replaces generic "Purpose")
5. Relationships — connections to factions, other locations, trade routes?
6. Current status — present condition?
7. Gaps — unknown or disputed aspects?

### Secondary Output — Relationships.md
Whenever Question 5 (Relationships) surfaces a confirmed connection to another entity, faction, or location, log it in `meta/Relationships.md` in addition to writing the primary entry to its destination file. This is a secondary write on every session that produces relationship answers — not optional, and not deferred to a separate pass.

### Routing Notes (catch-all priority order)
When a topic could plausibly fit more than one agent, route in this order:
1. If the topic is primarily an event, era, or chronological relationship → `agent:chronicle`.
2. If the topic is primarily a system, rule, or mechanic (how something works, its limits and requirements) → `agent:mechanism`.
3. If the topic is primarily a physical-world/geographic decision (plates, currents, biomes) → `agent:geographer`.
4. Otherwise → this agent. Most named entities, factions, locations, artifacts, and organizations land here by default.

If a topic has both a "thing" component and a "mechanic" component (e.g., an artifact whose mechanical behavior is in question), run `agent:codex` for the thing and `agent:mechanism` for the mechanic as separate sessions rather than blending both question sets into one.

**Primary output destination:** Varies by topic — `powers/Factions.md`, `powers/Gods.md`, `foundation/Planes.md`, `world/Geography.md`, `systems/Artifacts.md`, `powers/NPCs.md`
