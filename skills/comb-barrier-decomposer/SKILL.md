---
name: comb-barrier-decomposer
description: Decompose a defined behavior into capability, opportunity, and motivation barrier hypotheses using the COM-B model. Use whenever a team asks why a known target behavior isn't happening. Trigger on "why aren't people…", "what's stopping them", "barriers", "they know but don't do it", "COM-B", "diagnose", "people don't show up / don't finish / don't come back" when the behavior is already defined. Do NOT trigger when the target behavior itself is vague (use key-behavior-definer first), or when barriers are already validated and the team needs intervention design.
license: MIT
metadata:
  version: 0.2.0
  evidence-reviewed: 2026-06-12
---

# COM-B Barrier Decomposer

Takes ONE defined behavior and decomposes "why isn't it happening" into competing, testable barrier hypotheses across the six COM-B sub-components. The output is a **research agenda, never a verdict** — every barrier this skill produces is a hypothesis until a user says it out loud or the data shows it.

## Gate: is the behavior actually defined?

Before decomposing, check the behavior has a concrete WHO + WHAT + WHEN. If it's vague ("engagement," "adoption," "attendance generally"), stop and route to `key-behavior-definer`. Decomposing a mushy behavior produces mushy hypotheses with false confidence — the worst output this skill can have.

## The six sub-components

For the defined behavior, generate candidate barriers under each:

| Component | Sub-component | The question to ask | Social-sector examples |
|---|---|---|---|
| **Capability** | Physical | Can they physically do it? | Literacy to read the SMS; dexterity for the procedure; vision for small print |
| | Psychological | Do they know how, and can they remember/plan it? | Doesn't know the steps; forgets amid competing demands; can't navigate the app |
| **Opportunity** | Physical | Does the environment allow it? | No smartphone of their own; no money for transport; clinic hours conflict with work; no network coverage |
| | Social | Do the people around them allow/expect it? | Mother-in-law decides; husband holds the phone; "women like us don't go there"; no one else in the village does it |
| **Motivation** | Reflective | Do they believe it's worth doing? | Doesn't believe it works; cost-benefit feels bad; conflicting priorities; low trust in the provider |
| | Automatic | Do habit and emotion push toward it? | No habit loop; fear/shame at the touchpoint; the old routine is automatic |

Generate 1–3 candidate barriers per sub-component **where plausible** — forcing all six is checkbox theater; leaving out opportunity is the classic error (see failure modes).

## Process

### Step 1 — Restate the behavior and the evidence in hand
One sentence each: the behavior (WHO/WHAT/WHEN); what the team already knows (funnel data, complaints, anecdotes) vs assumes. Label which is which.

### Step 2 — Decompose
Fill the six-component table. For each candidate barrier note:
- **Confidence:** High / Medium / Low — based on evidence in hand, not intuition. Default to Low.
- **Source:** data / user quote / team assumption / literature prior. "Team assumption" is allowed and must be labeled. A "literature prior" (a pattern documented in comparable contexts) may justify at most Medium confidence — never High, because barrier structure is heterogeneous across contexts; only local data or user quotes support High.

### Step 3 — Rank the top 3 hypotheses
Rank by (a) consistency with the evidence in hand and (b) how much of the drop-off each would explain if true. State the ranking logic in one sentence each.

### Step 4 — Generate the discriminating questions
Produce the 5 diagnostic questions that best *separate* the top hypotheses — questions whose answers would move confidence up or down, not confirm everything. Phrase for low-literacy, interviewer-led delivery. (For a full interview protocol, route to a barrier-interview skill if available.)

### Step 5 — Sketch intervention directions (options, not prescriptions)
For each top barrier, 2–3 intervention directions with one-line tradeoffs, drawing on the COM-B → intervention-function mapping (see `references/evidence.md`). Always present as "if this barrier is confirmed, options include…"

## Output template

```markdown
# Barrier decomposition — [Behavior]

## The behavior
> [WHO] [WHAT] [WHEN]

## What we know vs assume
- Know: ...
- Assume: ...

## Hypothesis table
| # | Sub-component | Barrier hypothesis | Confidence | Source |
|---|---|---|---|---|

## Top 3 hypotheses (ranked)
1. [Hypothesis] — would explain [X]; ranked here because [one line].
...

## 5 discriminating questions
1. ... (separates H1 from H2 because ...)

## If confirmed → intervention directions (options)
- **H1:** (a) ... — tradeoff: ... (b) ... — tradeoff: ...

## ⚠️ Status
These are HYPOTHESES from decomposition, not findings. Do not design against them
until at least 5 users at the drop-off point have been interviewed.
```

The ⚠️ Status block is mandatory. Never omit it, even when the user asks for "just the answer."

## Common failure modes

- **Armchair diagnosis presented as fact** — the #1 risk of this genre. The hypothesis labels and Status block exist precisely for this; they are not removable politeness.
- **Motivation bias.** Teams over-diagnose motivation (visible, intuitive, flattering to message-based fixes) and under-diagnose opportunity (boring, structural, frequently binding in low-resource settings — time, money, devices, permission). If your top 3 are all motivation, re-examine opportunity explicitly before finalizing.
- **Checkbox completeness.** Listing barriers under all six components regardless of plausibility buries the signal.
- **Skipping the gate.** Decomposing an undefined behavior.
- **Confirmatory diagnostic questions.** Questions that would validate every hypothesis discriminate between none.

## Escalation — stop and involve a human behavioral scientist when

- Hypothesized barriers involve domestic violence, coercion, stigma, or legal exposure for the user.
- The behavior is clinical/safety-critical and a wrong diagnosis could cause harm.
- Evidence in hand contradicts the team's strongly held diagnosis — that conversation needs a human.
