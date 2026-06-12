---
name: key-behavior-definer
description: Define and prioritize a Key Behavior — the specific WHO + WHAT + WHEN action that drives a program outcome. Use whenever a project needs a target behavior defined, sharpened, or chosen between alternatives. Trigger on "what's our target behavior", "what should users actually do", "key behavior", "behavior to change", "pick a behavior", "is this a good target behavior", "what action should we drive", or when a team states a goal that contains no visible human action ("improve engagement", "raise awareness", "increase adoption", "empower caregivers"). Also trigger when prioritizing among candidate behaviors. Do NOT trigger for diagnosing why a defined behavior isn't happening (use comb-barrier-decomposer) or for designing the intervention itself.
license: MIT
metadata:
  version: 0.2.0
  evidence-reviewed: 2026-06-12
---

# Key Behavior Definer

A Key Behavior is the specific action a person must take to drive a desired outcome. It is the *how*, not the *what*. Get this wrong and everything downstream — diagnosis, intervention design, measurement — is built on sand.

A Key Behavior has three non-negotiable characteristics:

- **Observable** — externally visible. Not "understand," "trust," "feel confident."
- **Measurable** — you can count or detect it in data the organization has or can get.
- **Uncomfortably specific** — formatted as **WHO + WHAT + WHEN**.

Canonical examples:

- Consumer tech: *Watch a show within 7 seconds of opening the app* (Netflix); *new users add 7 friends within 10 days* (early Facebook).
- Social sector: *Caregiver of a child aged 3–6 completes one practice activity with their child within 24 hours of receiving the WhatsApp video*; *new mother initiates skin-to-skin contact within 1 hour of delivery*; *smallholder farmer registers for the weather-advisory line before the first sowing week*.

This skill draws on behaviour specification as the entry step of behaviour-change frameworks (see `references/evidence.md`). It outputs **options with tradeoffs, not a single decree** — the user's team makes the call.

## Decide your mode

**Interactive mode** — they want to think it through. Signals: "help me figure out the key behavior," no brief shared, or they ask to be walked through.
→ Walk the 4 steps conversationally. Pause after each step. Push back when answers are vague — precision is the entire value of this exercise.

**Batch mode** — they've provided input. Signals: they paste a brief, program description, or theory of change and say "give me candidate key behaviors."
→ Run all 4 steps internally, return the output template.

If unclear, ask once: "Want to walk through this together, or should I read what you've shared and propose candidates?"

## The 4-step process

### Step 1 — Identify the outcome

What end goal is the program pointed at? (School readiness, adherence to treatment, savings accumulation, immunization completion, re-enrollment.) The Key Behavior is *the lever* on the outcome — if you can't name the outcome, you can't judge any candidate. If multiple outcomes are in play, ask the user to pick one.

### Step 2 — List candidate actions

Brainstorm 5–10 candidate behaviors that could plausibly drive the outcome. Mix:

- **Early-funnel** (low commitment, easy to influence — but may not predict the outcome)
- **Mid-funnel** (committing, demonstrating intent)
- **Late-funnel** (close to the outcome — but often too late to intervene)

The sweet spot: early enough that you haven't lost most people before it, predictive enough that moving it moves the outcome.

Also surface **anti-behaviors** — actions that hurt the outcome (e.g., "shares the OTP with an agent," "skips the dose when feeling better"). Not targets, but they shape design.

### Step 3 — Get uncomfortably specific (WHO / WHAT / WHEN)

Pick the 1–3 strongest candidates and pin each component:

- **WHO** — which segment? Resist "all users/beneficiaries." Specify by enrollment stage, geography/language, device access (own phone vs shared), or program state.
- **WHAT** — a concrete verb. No abstractions.
- **WHEN** — a time window or trigger event. "Within X hours of Y." A vague WHEN is a tell that the behavior isn't ready.

Format: **[WHO] [WHAT] [WHEN]** — one sentence.

If you can't fill all three slots without hand-waving, go back to step 2.

**Hand-off rule:** when a request is really barrier diagnosis (behavior defined, "why isn't it happening"), route to `comb-barrier-decomposer` and stop — you may sharpen the WHO/WHAT/WHEN in one short paragraph, but do NOT produce your own barrier analysis. Reproducing another skill's job creates two half-versions of it.

### Step 4 — Double-check

Reject or rewrite any candidate where the answer is "yes":

1. **Is it an outcome in disguise?** ("Child is school-ready" — that's the outcome, not the lever.)
2. **Is it a thought, feeling, or belief?** Watch for: understand, trust, feel, believe, be aware, appreciate. Rewrite to the action that *proves* the internal state.
3. **Is it outside the org's influence?** No levers → academic.
4. **Is it unmeasurable in current data?** If yes, flag the instrumentation gap as a project risk — don't quietly drop the candidate.

## Prioritize among candidates

Score each finalist High / Medium / Low on:

- **Impact** — predicted effect on the outcome if this behavior moves
- **Drop-off** — how many people currently fail to do it (room to improve)
- **Control** — the org's ability to change the context around the action

Surface tradeoffs explicitly. Never hide them in an aggregate score, and never silently pick the safe option. Present the top candidate **and the runner-up** with the tradeoff stated.

## Output template

```markdown
# Key Behavior — [Program name]

## Outcome
[One sentence]

## Candidates considered
1. [Candidate] — [one line, funnel position]
...

## Prioritization
| Candidate | Impact | Drop-off | Control | Tradeoff notes |
|---|---|---|---|---|

## Recommended Key Behavior (+ runner-up)
- **WHO**: [segment]
- **WHAT**: [verb + object]
- **WHEN**: [trigger / window]

> [Full sentence]

**Runner-up:** [full sentence] — choose this instead if [condition].

## Validation hook (do this week)
Confirm the recommended behavior is countable in existing data. Name the table/report/log where it appears. If it appears nowhere, that instrumentation gap is your first project task.

## Anti-behaviors to watch
- ...
```

## Common failure modes

- **Hedging on WHEN** ("eventually," "during the program") — push for a window or trigger.
- **Thought-shaped behaviors** — ask "what would they *do* that proves it?"
- **Picking the outcome** — "completes immunization schedule" is the outcome; "attends the next scheduled camp within 7 days of the reminder" is a lever.
- **"All beneficiaries"** — defaults look safe, produce mush. Pick a segment.
- **The latest possible behavior** — correlates beautifully, but you've already lost everyone.

## Escalation — stop and involve a human behavioral scientist when

- The key behavior is clinical or safety-critical (medication dosing, danger-sign response, referral compliance).
- The behavior touches domestic power dynamics, stigma, or legal risk for the user.
- The team wants to target children's behavior directly rather than a caregiver's.
