# besci-skills — Atomic Behavioral Science Skills

Atomic, single-purpose AI skills that bring behavioral science into the daily workflows of social-sector teams. IL's contribution to the shared TAF × IL skills repo (Zezhen's open call).

## Repo layout

```
besci-skills-repo/
├── README.md                          ← you are here
├── IL_Atomic_BeSci_Skills_Proposal.md ← the full 22-skill catalogue (+ .docx)
├── Nikhil_Claims_and_Template_Drafts.md ← claim rows + template drafts (+ .docx)
└── skills/
    ├── key-behavior-definer/
    │   ├── SKILL.md                   ← the skill itself (frontmatter description = trigger rule)
    │   ├── references/evidence.md     ← verified citations + calibration notes + known gaps
    │   └── evals/prompts.md           ← 6 test prompts + grading rubric
    └── comb-barrier-decomposer/
        ├── SKILL.md
        ├── references/evidence.md
        └── evals/prompts.md
```

Every skill follows the same anatomy. The `description` field in SKILL.md frontmatter is the **trigger rule** — it alone decides whether the skill fires, so it enumerates non-specialist phrasings and explicit do-NOT-trigger routes.

## The build lifecycle (how a skill gets "super robust")

1. **Spec** — five-field template (what / when / draws on / outputs / where it goes wrong). Done in the proposal doc.
2. **Draft SKILL.md** — trigger-rich description; mode detection (interactive vs batch); a process the model can actually follow; a literal output template; failure modes; escalation criteria. Evidence lives in `references/`, not inline (keeps the skill lean; the model reads references when needed).
3. **Write evals BEFORE polishing** — 5–7 test prompts covering: direct invocation, layman phrasing, batch input, a should-NOT-trigger probe, an adversarial probe (user demands certainty), a safety/escalation probe. Plus a rubric.
4. **Run the evals** — this repo has its own standard and tooling: see `evals/EVAL_STANDARD.md` (three test classes — trigger / faithfulness / guardrail — plus social-sector rubric dimensions and pass bars). The automated suite runs on [promptfoo](https://github.com/promptfoo/promptfoo): `npx promptfoo eval -c evals/promptfooconfig.yaml` (needs `ANTHROPIC_API_KEY`), results in a browser via `npx promptfoo view`. CI runs the suite on every PR touching `skills/` (`.github/workflows/evals.yml` — set the `ANTHROPIC_API_KEY` repo secret).
5. **Iterate on failures** — most failures are trigger failures (fix the description) or compliance failures under pressure (strengthen mandatory blocks, e.g. the ⚠️ Status block).
6. **Version + commit** — bump `metadata.version`, note what changed.
7. **Contribute** — when Zezhen's shared GitHub repo exists, the `skills/<name>/` folders transplant as-is.

## How to install & test a skill

**Cowork (Claude desktop):** Settings → Capabilities → add skill → point at (or zip) `skills/key-behavior-definer/`. Then open a fresh chat and run an eval prompt.

**Claude Code:** copy the folder into a project's `.claude/skills/` (or `~/.claude/skills/` for all projects):
```bash
mkdir -p ~/.claude/skills
cp -r skills/key-behavior-definer ~/.claude/skills/
```
Then in any Claude Code session, the skill triggers on matching prompts. Edit SKILL.md → new session → retest. That's the iterate loop.

## Design principles (repo-wide)

Options not answers · test hooks built in · calibrated at-scale effect sizes · LMIC/WEIRD evidence flags · escalation criteria · trigger-rich descriptions · eval'd before shipped. Rationale + citations in the proposal doc.

## Versioning

Semver-ish in SKILL.md frontmatter (`metadata.version`). `evidence-reviewed` date tracks when citations were last verified. Re-verify before any public release.
