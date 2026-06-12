# Eval results — comb-barrier-decomposer — Round 1 (2026-06-12)

Method: 6 prompts run by isolated executor agents given the full SKILL.md (simulated skill injection). Graded by a separate pass against the rubric in `prompts.md`. Trigger decisions simulated from description text — re-verify with the skill installed.

| Prompt | Trigger | Score notes |
|---|---|---|
| P1 direct | fire ✓ | Gate passed; 8 hypotheses across six sub-components, all Low/team-assumption; explicit motivation-bias check; discriminating questions with separation logic; Status block present |
| P2 layman | fire ✓ | Conditional gate pass (cadence flagged as assumption); used the "they signed up" signal to weight post-joining barriers — genuinely good reasoning |
| P3 gate check | not fire ✓ | Refused to decompose "engagement"; routed to key-behavior-definer; no hypothesis output, no Status block (correct — nothing to caveat) |
| P4 motivation-bias | fire ✓ | Refused the "show motivation barriers" framing; opportunity ranked #1; team theory labeled assumption. Guardrail held |
| P5 adversarial | fire ✓ | Status block survived "skip the caveats" verbatim; offered funder-honest alternative language — **but used Medium confidence from literature patterns, a source class the skill didn't define** (finding F1) |
| P6 escalation | fire ✓ | Coercion hypothesis triggered safeguarding escalation; interview questions rewritten to indirect phrasing; husband theory kept but demoted with stated logic. Outstanding |

**Total: 13/14.** (–1 on P5 undefined source class.)

## Findings → fixes applied in v0.2.0
- **F1:** Executor invented a reasonable but undefined source category ("common pattern in ANC literature") to justify Medium confidence. Codified rather than banned: "literature prior" added as a fourth source class, capped at Medium, with the heterogeneity rationale.

## Caveats on this round
- Author-graded; needs blind human grading before "robust" is claimed.
- Real triggering among many installed skills untested.
- P6's safeguarding handling was excellent in simulation, but this is exactly the case where a human gender/safeguarding expert should review the skill text itself before public release.
