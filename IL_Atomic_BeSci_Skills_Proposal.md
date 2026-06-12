# Atomic BeSci Skills — IL Contribution Candidates

**For:** The shared TAF × IL behavioral science skills repo (Zezhen's open call)
**From:** Irrational Labs (Nikhil + team)
**Date:** June 2026 · **Status:** Draft for voting

---

## How to read this doc

Below are **22 candidate skills — 21 atomic, plus one deliberate composite** — each written in Zezhen's five-field template (*what it does / when it should be used / what it draws on / what it outputs / where it goes wrong*). They are chunked by where they sit in an NGO program team's workflow, because that's how a program designer or PM will reach for them — mid-task, not mid-literature-review.

Three things we did deliberately:

1. **Every citation is peer-reviewed and post-2000**, and every one was independently verified (authors, year, journal, headline numbers) before going in this doc. Where a finding has a published critique or failed replication, we say so in the skill itself — that's a feature, not a footnote.
2. **Atomicity is enforced**: each skill is one operation, describable in one sentence without "and". Where a candidate idea was secretly a workflow, we split it. The single exception — S22, an experiment-design walkthrough — is a composite by design, flagged as such, and exists because the atoms need one front door.
3. **No skill gives a definitive answer.** Every skill outputs a *ranked set of options with tradeoffs* plus the *cheapest validation step* (an A/B arm, a 5-user qual check, or a base-rate lookup). The skills are designed for the stated user — a program designer or PM at an NGO *without a behavioral scientist in the room* — which means the guardrails have to live inside the skill.

At the end: three things IL can contribute essentially immediately, our proposed top-8 shortlist for the vote, a collision map against already-claimed skills, and a counterfactual check on this whole list.

---

## Design principles we'd propose for the whole repo

These apply to every skill below and, we'd argue, every skill anyone contributes:

- **P1 — Options, not answers.** Every skill returns 2–4 ranked alternatives with tradeoffs, never a single prescription.
- **P2 — Test hooks built in.** Every skill ends with the cheapest way to check it worked: an A/B arm, a 5–8 user qualitative check, or a data lookup.
- **P3 — Calibrated evidence.** Cite at-scale effects, not lab best-cases. Academic nudge papers average +8.7pp; the same intervention classes run by government Nudge Units at scale average +1.4pp (DellaVigna & Linos 2022, *Econometrica*). Skills that quote lab numbers to NGOs set programs up to "fail" against fantasy benchmarks.
- **P4 — Generalizability flag.** Each skill states where its evidence comes from and whether non-WEIRD/LMIC replications exist (Henrich, Heine & Norenzayan 2010, *Behavioral and Brain Sciences*; Bryan, Tipton & Yeager 2021, *Nature Human Behaviour*).
- **P5 — Escalation criteria.** Each skill names the situations where the user should stop and consult a human behavioral scientist (high-stakes/clinical decisions, vulnerable populations, signs of backfire).
- **P6 — Trigger-rich descriptions.** A skill's description field determines whether it fires at all — the single biggest practical failure mode in skill libraries. Descriptions must enumerate non-specialist phrasings ("why aren't people showing up", not "diagnose volitional barriers").
- **P7 — Eval'd before shipped.** Each skill ships with 3–5 test prompts and an expected-output rubric. IL can contribute its existing skill-creation eval harness for this (see "Ready to port").

---

## The workflow map

The 21 skills sit in five stages of a program team's actual workflow. Atomic skills compose: a typical path is S1 → S3 → S4 → (one of S6–S14) → S16 → S17 → S18 → S20.

**DEFINE** (what exactly is the behavior?) → **DIAGNOSE** (why isn't it happening?) → **DESIGN** (what intervention?) → **CALIBRATE** (will it work *here*, and how big, honestly?) → **TEST & LEARN** (run the cheapest real test)

---

# Stage 1 — DEFINE

## S1. Key Behavior Definer ⭐ *(exists at IL — ready to port)*

1. **What it does:** Turns a vague program goal into one observable, measurable, uncomfortably specific WHO + WHAT + WHEN key behavior.
2. **When it should be used:** Project kickoff or any moment of "what's our target behavior", "what should users actually do", "our goal is engagement" (a goal, not a behavior). Trigger phrases: *target behavior, key behavior, what action, behavior to change, what should we get users to do.*
3. **What it draws on:** IL's 3B methodology (Key Behavior → Reduce Barriers → Amplify Benefits), battle-tested across 40+ client engagements and already encoded as a working IL skill; behaviour specification as the entry step of the Behaviour Change Wheel (Michie, van Stralen & West 2011, *Implementation Science*). Evidence base is methodological rather than WEIRD-skewed, but IL's canonical examples are US tech products — needs LMIC examples added (e.g., "caregiver completes one practice activity with child within 24h of receiving the WhatsApp video").
4. **What it outputs:** 3–5 candidate key behaviors, each scored on an Impact / Drop-off / Control prioritization grid; a recommended pick *with the runner-up preserved*; validation hook: confirm this week that the behavior is actually countable in your existing data — if it isn't, that's your first finding.
5. **Where it goes wrong:** Users smuggle outcomes back in ("improve health literacy" is not a behavior); "uncomfortably specific" gets negotiated away in teams; picks a behavior the org can't observe. Escalate to a human when the key behavior is clinical or safety-critical.

## S2. Funnel Leak Finder

1. **What it does:** Locates the single biggest behavioral drop-off in a program funnel from step-by-step conversion numbers.
2. **When it should be used:** "Where are we losing people?", reviewing engagement/retention dashboards, deciding which step of onboarding to fix first.
3. **What it draws on:** The hassle-factor/assistance literature: in the H&R Block FAFSA experiment, *assistance* with the form raised college enrollment ~8pp while information alone did nothing (Bettinger, Long, Oreopoulos & Sanbonmatsu 2012, *QJE*) — drop-off is usually friction, not motivation; last-mile behavioral design framing (Datta & Mullainathan 2014, *Review of Income and Wealth*). LMIC-relevant by construction.
4. **What it outputs:** Ranked leak table with the mechanism hypotheses (2–3 per leak: friction / comprehension / motivation / technical failure) and what evidence would discriminate between them; an instrumentation gap list; validation hook: 5 short interviews with users who stalled at exactly the biggest leak, before designing anything.
5. **Where it goes wrong:** Hallucinated "benchmark" conversion rates (the skill must refuse to invent industry baselines); mistaking *technical* drop-off for *behavioral* drop-off — check delivery logs first. We learned this expensively: an experiment arm that "showed null" turned out never to have been delivered.

---

# Stage 2 — DIAGNOSE

## S3. COM-B Barrier Decomposer *(the doc's own flagship example — currently unclaimed)*

1. **What it does:** Decomposes one defined behavior into competing barrier hypotheses across capability, opportunity, and motivation.
2. **When it should be used:** Behavior is defined (S1 done) but "why aren't they doing it" is folk theory. Triggers: *why aren't people..., what's stopping them, barriers, COM-B, diagnose.*
3. **What it draws on:** The COM-B model and Behaviour Change Wheel (Michie, van Stralen & West 2011, *Implementation Science*) — six sub-components: physical/psychological capability, physical/social opportunity, reflective/automatic motivation; each barrier class maps onward to intervention functions via the 93-technique BCT Taxonomy v1 (Michie et al. 2013, *Annals of Behavioral Medicine*). Framework origin is UK health policy — widely applied in LMIC implementation research, but the skill should say the mapping is a reasoning scaffold, not an empirical law.
4. **What it outputs:** A barrier hypothesis table with explicit confidence levels and — critically — labeled as *hypotheses, not findings*; the 5 diagnostic questions that would best discriminate between the top hypotheses (feeding S4); 2–3 intervention directions per confirmed barrier class, as options.
5. **Where it goes wrong:** Armchair diagnosis presented as fact (the #1 risk of this entire genre); systematically over-weighting motivation (visible, intuitive) versus opportunity (boring, often binding in low-resource settings — see the behavioral development economics survey by Kremer, Rao & Schilbach 2019, *Handbook of Behavioral Economics*, flagged: handbook chapter, not journal-refereed).

## S4. Barrier Interview Guide Builder

1. **What it does:** Generates a 20-minute semi-structured interview guide that tests which hypothesized barriers actually bind.
2. **When it should be used:** Immediately after S3, before any design work. Triggers: *how do we check which barrier is real, user interviews, talk to users, validate barriers.*
3. **What it draws on:** Cognitive interviewing and probing-technique evidence (Beatty & Willis 2007, *Public Opinion Quarterly*); behavioral diagnosis practice in development programs (Datta & Mullainathan 2014, *Review of Income and Wealth*). **Adjacency note:** Zezhen has claimed a *cognitive interview script generator* — that targets survey-item pretesting; this targets barrier diagnosis. Related machinery, different atomic operation; the two skills should cross-reference.
4. **What it outputs:** An interview guide with neutral openers, barrier-discriminating probes (not confirmatory ones), low-literacy and translated phrasing variants, and an analysis grid mapping answer patterns back to S3's barrier table; validation hook: pilot on 2 users and check whether any question telegraphs its desired answer.
5. **Where it goes wrong:** Leading questions that confirm the team's pet barrier; social desirability — respondents performing gratitude for the NGO; translation artifacts that change question meaning; treating 5 interviews as prevalence estimates.

## S5. Cognitive Load Auditor

1. **What it does:** Audits one form, flow, or message for the cognitive bandwidth it demands from a user living with scarcity.
2. **When it should be used:** Reviewing application forms, onboarding flows, multi-step instructions, anything users must complete under financial or time stress. Triggers: *too complicated, simplify this, users don't finish the form, cognitive load.*
3. **What it draws on:** Scarcity-and-bandwidth research: scarcity focuses attention on the focal demand and causes neglect and over-borrowing elsewhere (Shah, Mullainathan & Shafir 2012, *Science*); poverty and cognitive function (Mani, Mullainathan, Shafir & Zhao 2013, *Science*) — **flagged honestly:** the famous farmer result has a published critique (Wicherts & Scholten 2013) and failed conceptual replications (e.g., Carvalho et al. 2016), so the skill treats it as suggestive. The *design implication* — minimize cognitive demands, especially at moments of financial stress — is low-regret either way.
4. **What it outputs:** A load-hotspot map (decisions required, memory demands, calculations, jargon, documents to fetch); 2–3 simplification options per hotspot ranked by effort; timing advice (when in the month/season to ask, not just what to ask); validation hook: a 5-user teach-back comprehension test.
5. **Where it goes wrong:** Conflating low literacy with low intelligence — simplification becoming condescension; stripping information users genuinely need; ignoring that *when* you ask can matter as much as *how*.

---

# Stage 3 — DESIGN

*Mechanism-level micro-skills. Each takes a diagnosed barrier and produces intervention options. They compose with (rather than duplicate) Kelly's claimed framework-level skills — intervention mapping and theory of planned behavior message customizers.*

## S6. Reminder Designer

1. **What it does:** Designs timing, frequency, and content options for one reminder message stream.
2. **When it should be used:** Any "send them a reminder" moment: adherence, re-engagement, appointments, savings deposits. Triggers: *reminder, nudge them, follow-up message, people forget.*
3. **What it draws on:** Strong, LMIC-heavy evidence. Savings reminders raised balances ~6%, with goal-mention content working best (Karlan, McConnell, Mullainathan & Zinman 2016, *Management Science*); weekly SMS raised ART adherence +13pp in Kenya while *daily* reminders did nothing — dosage matters (Pop-Eleches et al. 2011, *AIDS*); calibration from the flu megastudy: average text effect ≈ +2pp / ~5% relative, best arm ~+4.5pp (Milkman et al. 2021, *PNAS*).
4. **What it outputs:** 3 variants varying timing and content (with the *weekly-beats-daily* dosage warning built in); WhatsApp-specific constraints surfaced (template approval, 24-hour windows); a ready-to-run A/B plan with expected effect range from the calibrated literature.
5. **Where it goes wrong:** Reminder fatigue and opt-outs (the cost is permanent channel loss, not just one ignored message); assuming the barrier is forgetting when it's something else — if S3 hasn't been run, the skill should ask; copying US send-time heuristics into contexts with shared phones and different daily rhythms.

## S7. Planning Prompt Builder

1. **What it does:** Converts a user's stated intention into a concrete when-where-how plan prompt.
2. **When it should be used:** The intention–action gap: people say yes and don't show up. Triggers: *they said they'd come, no-shows, follow-through, they agree but don't do it.*
3. **What it draws on:** Implementation intentions meta-analysis, d = 0.65 across 94 tests (Gollwitzer & Sheeran 2006, *Advances in Experimental Social Psychology* — flagged: book-series chapter, and lab-heavy); field calibration: date-and-time flu shot prompts +4.2pp (Milkman et al. 2011, *PNAS*); plan-making call scripts +4.1pp turnout (Nickerson & Rogers 2010, *Psychological Science*). Field effects are roughly a tenth of the lab d — the skill says so.
4. **What it outputs:** 2–3 plan-prompt scripts (chatbot message, IVR, or interviewer-led) with slot-filling structure (which day? what time? how will you get there?); a fallback for users who can't control logistics; an A/B hook against a standard encouragement message.
5. **Where it goes wrong:** Backfires or annoys when the user lacks actual control over the logistics (an *opportunity* barrier wearing a motivation costume); plan questions can feel surveillance-like from an authority; treating the lab d = 0.65 as the expected field effect.

## S8. Social Norm Message Checker

1. **What it does:** Drafts and risk-checks a social-norm message against the actual local base rate of the behavior.
2. **When it should be used:** Whenever anyone proposes "most people are doing X" messaging. Triggers: *social proof, everyone else is, norm message, peer comparison.*
3. **What it draws on:** Home energy reports −2% consumption (Allcott 2011, *Journal of Public Economics*); the boomerang effect — descriptive norms *increased* consumption among below-average users until an injunctive signal was added (Schultz, Nolan, Cialdini, Goldstein & Griskevicius 2007, *Psychological Science*); when norm-nudges fail or backfire (Bicchieri & Dimant 2022, *Public Choice*); upper bound on social-pressure effects: the "Neighbors" mailer +8.1pp (Gerber, Green & Larimer 2008, *APSR*).
4. **What it outputs:** Step one, non-negotiable: *what is the real base rate?* If the desirable behavior is a minority behavior, the skill blocks the descriptive norm and offers alternatives (injunctive norms, dynamic/trending norms); otherwise 2–3 message variants with reference-group choices and explicit backfire flags; validation hook: A/B with a no-norm control, monitoring the below/above-average segments separately.
5. **Where it goes wrong:** Fabricated norms — unethical and trust-destroying when discovered; boomerang for users already above average; reference-group mismatch (a national statistic means nothing to a village identity); norms about contested behaviors triggering reactance.

## S9. Incentive Menu Designer

1. **What it does:** Builds a menu of incentive options — size, type, schedule — for one behavior, with crowd-out risks flagged.
2. **When it should be used:** "Should we pay people to do X?" conversations, designing attendance or completion rewards. Triggers: *incentive, reward, pay them, prize, lottery.*
3. **What it draws on:** When and why incentives work and backfire (Gneezy, Meier & Rey-Biel 2011, *Journal of Economic Perspectives* — flagged: invited review); the canonical LMIC result: small in-kind incentives (lentils) at reliable immunization camps took full immunization from 18% (camps alone) to 39%, versus 6% in control — and were *more* cost-effective per child (Banerjee, Duflo, Glennerster & Kothari 2010, *BMJ*).
4. **What it outputs:** 3–4 options across cash / in-kind / lottery / social recognition, each with predicted failure modes (crowd-out of intrinsic motivation, gaming of the metric, fairness perceptions among non-recipients, expectations that outlast the budget); a smallest-viable-test design comparing the top two against no-incentive.
5. **Where it goes wrong:** Crowding out intrinsic motivation in pro-social domains; incentivizing the measurable proxy instead of the behavior; creating entitlement cliffs when funding ends; per-unit incentives meeting shared community resources.

## S10. Commitment Device Designer

1. **What it does:** Designs a soft-to-hard ladder of commitment options for a goal the user already holds.
2. **When it should be used:** Follow-through gaps on *self-set* goals: savings targets, course completion, cessation. Triggers: *they want to but don't, commitment, deposit, pledge.*
3. **What it draws on:** SEED commitment savings in the Philippines: +81% balances at 12 months (ITT of the offer; take-up ~28%; effect attenuated by 2.5 years) (Ashraf, Karlan & Yin 2006, *QJE*); CARES smoking deposits: +3.3–5.8pp quit rates ITT — but 66% of takers forfeited their deposits (Giné, Karlan & Zinman 2010, *AEJ: Applied*).
4. **What it outputs:** A commitment ladder (public pledge → self-set deadline → deposit contract) with honest take-up expectations (commitment products are chosen by 11–28% of people, not everyone); explicit harm warning on hard devices — the people who fail forfeit real money; a pilot design that tracks forfeiture, not just take-up.
5. **Where it goes wrong:** Hard commitments hurting exactly the people they fail; deploying commitment for externally imposed goals (it only works for wanted ones); celebrating take-up while ignoring forfeiture rates; tying up poor households' liquidity buffers.

## S11. Default & Friction Restructurer

1. **What it does:** Identifies where one choice point can be restructured through defaults or friction changes instead of persuasion.
2. **When it should be used:** Any enrollment, form, allocation, or renewal decision. Triggers: *default, opt-in vs opt-out, pre-select, make it automatic, too many steps.*
3. **What it draws on:** The strongest evidence class in the behavioral toolkit: meta-analysis of 58 default studies, average d = 0.68 (Jachimowicz, Duncan, Weber & Johnson 2019, *Behavioural Public Policy*); the organ-donation policy contrast (Johnson & Goldstein 2003, *Science* — flagged: 1-page Policy Forum, and stated *consent* ≠ actual donation, where later evidence is mixed); crucially, defaults are the intervention class that *survives at scale* (DellaVigna & Linos 2022, *Econometrica*).
4. **What it outputs:** A choice-point map of the flow; default/friction restructuring options each with an ethical guardrail check (easy reversal, transparency, alignment with the user's own interest); calibrated expected magnitude (large by nudge standards, heterogeneous — the meta includes null and two negative results); validation hook: the cleanest A/B in the catalogue.
5. **Where it goes wrong:** Defaults set against users' interests (the dark-pattern line is one careless decision away — this skill needs the strongest escalation criteria in the repo); removing friction that served as useful deliberation; defaults on decisions communities expect to make actively and collectively.

## S12. Messenger Selector

1. **What it does:** Recommends who should deliver one message — peer, community health worker, authority figure, or local influencer.
2. **When it should be used:** Choosing the sender, voice, or face for any campaign or content. Triggers: *who should say this, trusted messenger, should the doctor or the peer say it.* (Live for us right now: RL Experiment 3 tests peer-parent vs anganwadi-worker videos.)
3. **What it draws on:** Network-central "gossips" nominated by villagers produced significantly wider diffusion than random or status-based seeds across 521 Haryana villages (Banerjee, Chandrasekhar, Duflo & Jackson 2019, *Review of Economic Studies*) — directly LMIC, directly relevant.
4. **What it outputs:** A messenger options matrix scoring credibility, identification ("someone like me"), reach, and cost; a recommendation *pair* (not a single answer) with the contexts in which each wins; validation hook: a cheap two-arm horse race, which is exactly the test we have in the field now.
5. **Where it goes wrong:** Importing WEIRD authority assumptions (the white coat doesn't carry identically everywhere); messenger effects confounded with production quality in video content; reach-optimized influencers lacking trust for sensitive topics; same-gender/caste/community matching effects ignored.

## S13. Fresh Start Timing Picker

1. **What it does:** Picks salient temporal landmarks for launching or relaunching one behavior campaign.
2. **When it should be used:** "When should we launch?", scheduling enrollment pushes or restart messages. Triggers: *timing, launch date, new year, when to send.*
3. **What it draws on:** The fresh start effect — aspirational behavior (gym visits, goal commitments, "diet" searches) spikes after temporal landmarks (Dai, Milkman & Riis 2014, *Management Science*). **Flagged: the weakest evidence base in this catalogue** — archival/correlational field data plus lab studies, and the skill says so out loud. Landmark localization matters: Diwali, Eid, harvest end, school year start, payday — not January 1.
4. **What it outputs:** 3 candidate launch moments with rationale and the local-calendar mapping; an explicit evidence-strength caveat; validation hook: staggered launch = a natural experiment for free.
5. **Where it goes wrong:** Treating the US calendar as universal; fresh-start framing disrupting *successful ongoing* streaks; over-investing in timing optimization when content and channel dominate.

## S14. Values Affirmation Drafter *(the doc's own example — currently unclaimed)*

1. **What it does:** Drafts a brief values-affirmation writing or reflection exercise adapted to a target population.
2. **When it should be used:** When identity threat plausibly suppresses engagement: stigma, stereotype threat, "programs like this aren't for people like me." Triggers: *affirmation, identity threat, stereotype, belonging.*
3. **What it draws on:** The original striking result: a 15-minute values-writing exercise reduced the Black–White GPA gap ~40% (Cohen, Garcia, Apfel & Master 2006, *Science*); theory review (Cohen & Sherman 2014, *Annual Review of Psychology*); **and the honest counterweight:** a well-powered district-wide replication found *no detectable overall effect*, with effects appearing context-dependent (Hanselman, Rozek, Grigg & Borman 2017, *Journal of Educational Psychology*). This skill is the catalogue's poster child for "options + caveats, never definitive."
4. **What it outputs:** 2 exercise variants (written and verbal/low-literacy); the specific conditions under which effects did vs didn't appear (threat present, timely delivery, psychological ambiguity preserved); a *strong* recommendation to pilot before scaling, with a pre-specified outcome.
5. **Where it goes wrong:** The most likely skill in this list to produce nothing — fragile, moderator-dependent effects; values lists that don't translate across cultures; mechanical administration destroying the psychological ingredient; teams scaling a null because the theory is appealing.

---

# Stage 4 — CALIBRATE *(cross-cutting)*

## S15. Evidence Generalizability Checker

1. **What it does:** Assesses whether the evidence behind one proposed intervention transports to your population and delivery context.
2. **When it should be used:** "This worked in the US / in a paper / for Duolingo — will it work here?" Before adopting any borrowed intervention. Triggers: *will this work here, evidence for our context, has this been tested in India.*
3. **What it draws on:** WEIRD sampling critique (Henrich, Heine & Norenzayan 2010, *Behavioral and Brain Sciences*); the heterogeneity revolution — treatment effects vary systematically and replication "failures" are expected without understanding moderators (Bryan, Tipton & Yeager 2021, *Nature Human Behaviour*); lab-to-scale attenuation (DellaVigna & Linos 2022, *Econometrica*). **Complementarity note:** Patricia has claimed a *cultural psychology lens* skill — hers audits the design through cultural-psych theory; this one audits the *evidence* (samples, settings, scale). They should cross-reference.
4. **What it outputs:** A gap report across four transport dimensions — population, delivery channel, scale, outcome distance — with a verdict in three grades: *adopt* (close match), *adapt* (theory transfers, surface doesn't), *pilot-first* (evidence is too far away); plus a minimal pilot design for the third case.
5. **Where it goes wrong:** False precision — transportability can't be computed, only flagged; the cynicism failure mode where nothing ever passes and teams are paralyzed (the output must always include the *least-bad* option); treating "no LMIC evidence" as "won't work" rather than "test first."

## S16. Effect Size Reality Checker

1. **What it does:** Converts a published effect size into a realistic expectation for your deployment, and the sample size that expectation implies.
2. **When it should be used:** Writing proposals, setting KPIs with funders, deciding whether a test is worth running. Triggers: *what lift should we expect, the paper says 25%, is this worth testing, set targets.*
3. **What it draws on:** The calibration literature, post-2020 and bracing: choice-architecture meta-analysis d = 0.43 (Mertens, Herberz, Hahnel & Brosch 2022, *PNAS*) versus *no evidence of an overall effect* after publication-bias correction (Maier et al. 2022, *PNAS* — itself a Bayesian model-averaging exercise); academic papers +8.7pp vs Nudge Units at scale +1.4pp (DellaVigna & Linos 2022, *Econometrica*); megastudies where the average text nudge moved vaccination ~+2pp and experts systematically overestimated effects (Milkman et al. 2021, *Nature*; Milkman et al. 2021, *PNAS*). The skill's engine is explicitly Bayesian: the published literature is your *prior*, not your prediction — and the right prior is the bias-corrected, at-scale-adjusted one. Design analysis with realistic priors also exposes the two errors that haunt small NGO experiments: Type S (your significant result has the wrong *sign*) and Type M (the exaggeration ratio — significant estimates from noisy studies systematically overstate true effects) (Gelman & Carlin 2014, *Perspectives on Psychological Science*).
4. **What it outputs:** A calibrated three-point range — optimistic / realistic / null-plausible — framed as a prior distribution in plain language ("before your test, the smart money is on +1–3pp; +10pp would be surprising"); the Type M warning made concrete ("if you run n=500 and get a significant result, expect that estimate to be ~3× the true effect"); what each scenario implies for sample size (feeding S18); funder-honest language for proposals ("published estimates range X–Y; at-scale analogues suggest Z; we will test").
5. **Where it goes wrong:** Over-deflation killing justified ambition — some interventions DO produce large effects (lentils + camps doubled immunization, Banerjee et al. 2010; phone tutoring delivered ~0.89 SD learning per $100, Angrist, Bergman & Matsheng 2022, *Nature Human Behaviour*) — the skill must distinguish "light-touch message nudge" from "structural redesign"; crude domain corrections applied across very different intervention classes.

---

# Stage 5 — TEST & LEARN

*Our strongest conviction: testing infrastructure is a foundational capability for the target user, not an appendix. These four skills are where "no behavioral scientist in the room" gets safest.*

## S17. Message A/B Test Designer

1. **What it does:** Turns one message decision into a runnable randomized test for a chatbot, SMS, or WhatsApp program.
2. **When it should be used:** "Which version should we send?" — the answer is almost always "test it." Triggers: *A/B test, which message works, experiment, test variants.* (We run these weekly on WhatsApp programs; this skill encodes that practice.)
3. **What it draws on:** At-scale embedded experimentation practice as documented across 126 Nudge Unit RCTs (DellaVigna & Linos 2022, *Econometrica*); design fundamentals: randomization unit, contamination, runtime (with power from S18, analysis integrity from S19).
4. **What it outputs:** 2–4 arms including a holdout, with each arm differing on *one* thing; randomization-unit recommendation with a contamination check (shared phones, village-level spillover → cluster); delivery-confirmation instrumentation — verify messages actually went out before believing any result (the silent killer; see S2/S20); runtime estimate; analysis spec feeding S19.
5. **Where it goes wrong:** Randomizing at the wrong unit; peeking and stopping early on noise; arms that differ on three things at once (uninterpretable); testing trivia while the program bleeds users at a step upstream (run S2 first).

## S18. Power & MDE Calculator

1. **What it does:** Computes the sample size one test needs, or the smallest effect a given sample can detect.
2. **When it should be used:** Before any test, full stop. Triggers: *is n=400 enough, sample size, how long to run, can we detect.*
3. **What it draws on:** Design-based power improvements — ANCOVA over difference-in-differences, multiple follow-ups for noisy outcomes (McKenzie 2012, *Journal of Development Economics*); calibrated priors from S16 (if at-scale analogues suggest +1–3pp, powering for +10pp is self-deception); the dual-language framing of design questions — frequentist power/MDE alongside Bayesian estimation with credible intervals and a region of practical equivalence (Kruschke & Liddell 2018, *Psychonomic Bulletin & Review*). **This is a procedural skill: it ships with a script and runs code — an LLM must never freehand power arithmetic.**
4. **What it outputs:** An MDE table across scenarios (effect size × clustering/ICC × attrition); **the same answer in both statistical languages**, because they serve different audiences: the *frequentist readout* for protocols and funders ("with n=4,000 and 80% power you can detect a 3.5pp lift at α=0.05") and the *Bayesian readout* for the team's actual decision ("with n=4,000, if the true effect is the realistic prior from S16, you'll end the test ~85% sure the effect is positive — and a flat result will rightly move your belief most of the way toward 'smaller than 1pp'"); options when underpowered: proximal outcomes, within-subject designs, longer runtime, or honestly not running the test.
5. **Where it goes wrong:** Hand-waved ICC assumptions flipping conclusions; powering on lab effect sizes; the subtler failure — running the underpowered test anyway and then *interpreting* the null (see S20); attrition ignored until analysis; Bayesian language misused as a license to stop early on hopeful posteriors (stopping rules still belong in S19).

## S19. Pre-Analysis Plan Drafter

1. **What it does:** Drafts a one-page pre-analysis plan for one simple experiment.
2. **When it should be used:** After design is locked (S17/S18), before launch. Triggers: *pre-register, analysis plan, how will we judge this, what counts as success.*
3. **What it draws on:** PAPs constrain data-mining and specification search, with honest costs acknowledged (Olken 2015, *Journal of Economic Perspectives* — flagged: solicited review); the canonical demonstration: in the Sierra Leone GoBifo evaluation the PAP prevented two divergent, equally plausible wrong interpretations of the same data (Casey, Glennerster & Miguel 2012, *QJE*).
4. **What it outputs:** One page: a single primary outcome, the estimation approach in plain language, subgroups declared in advance (or explicitly none), a multiple-testing stance, a stopping rule, and what result triggers what decision. Proportionate by design — one page for a message test, not forty.
5. **Where it goes wrong:** Over-engineering small program tests until teams skip planning entirely (proportionality is the point); PAP theater — written, filed, ignored at analysis time; ambiguous outcome definitions that quietly recreate the garden of forking paths.

## S20. Null Result Diagnostician

1. **What it does:** Diagnoses why one experiment showed no effect, separating implementation, power, measurement, and theory failures — in that order.
2. **When it should be used:** "It didn't work." Before killing a program, before blaming the theory, before the post-mortem meeting. Triggers: *no effect, null result, the test failed, didn't move the needle.*
3. **What it draws on:** Heterogeneity framing — a null average can hide real effects in subgroups and contexts (Bryan, Tipton & Yeager 2021, *Nature Human Behaviour*); systematic attenuation at scale (DellaVigna & Linos 2022, *Econometrica*); and our own scar tissue: a "null" arm that was never delivered. Implementation failure masquerades as theory failure constantly, and almost no one checks in the right order.
4. **What it outputs:** A fixed-order decision-tree walk: (1) delivery logs — did it reach people? (2) exposure — did they open/see it? (3) power — what could this test even detect (from S18) vs what was plausible (from S16)? (4) measurement — could the outcome move and your instrument miss it? (5) only then, theory. Verdict plus the next cheapest experiment that discriminates between surviving explanations.
5. **Where it goes wrong:** Motivated-reasoning rescue ("it really works, the test was just bad") — the skill requires pre-committed standards (S19) to cite back; the opposite failure: killing a sound program off one underpowered null; post-hoc subgroup fishing dressed up as "heterogeneity analysis."

## S21. Rapid Qual Pretest Designer

1. **What it does:** Designs a 5–8 user qualitative pretest of one piece of program content before launch.
2. **When it should be used:** A new message, video, or flow is about to ship to thousands of people and no real user has seen it. Triggers: *pretest, will people get this, user check, before we send it.*
3. **What it draws on:** Think-aloud and probing methods (Beatty & Willis 2007, *Public Opinion Quarterly*); analysis via thematic analysis (Braun & Clarke 2006, *Qualitative Research in Psychology* — note their later "reflexive TA" refinements). **Adjacency note:** Zezhen's cognitive interview script generator targets survey items; this targets program content. Cross-reference, don't duplicate.
4. **What it outputs:** A recruitment spec optimizing for *heterogeneity* (the skeptic, the low-literacy user, the edge case — not eight enthusiasts); a protocol covering comprehension (teach-back), interpretation ("what is this asking you to do?"), and honest-persuasion probes; a one-page synthesis grid; explicit go / fix / kill criteria agreed before the interviews.
5. **Where it goes wrong:** Convenience-sampling the friendliest users; pretest theater — running it and shipping unchanged regardless; treating 6 interviews as effect-size evidence (it screens for catastrophe and confusion, it does not measure impact).

## S22. Experiment Design Walkthrough ⭐ *(the one deliberate molecule)*

1. **What it does:** Walks a non-specialist from a defined key behavior and a set of intervention ideas to a complete, honestly-powered experimental design plan.
2. **When it should be used:** "We know what behavior we want and we have ideas — how do we set up a proper test?" Triggers: *design our experiment, set up a test, we have three ideas, experiment plan, pilot design.* This is the front door for users who would never invoke five atomic skills in sequence.
3. **What it draws on:** This skill is **deliberately not atomic** — it is the orchestrating layer that composes S16 → S17 → S18 → S19 in a guided conversation, and we flag that openly (it directly answers the "maybe orgs want the molecule, not the atoms" objection in our counterfactual check). Its statistical spine: calibrated priors and Type S/M design analysis (Gelman & Carlin 2014, *Perspectives on Psychological Science*); frequentist and Bayesian design framings as complements, not rivals (Kruschke & Liddell 2018, *Psychonomic Bulletin & Review*); ANCOVA and repeated measurement for power (McKenzie 2012, *Journal of Development Economics*); proportionate pre-analysis discipline (Olken 2015, *JEP*; Casey, Glennerster & Miguel 2012, *QJE*).
4. **What it outputs:** A one-page design plan assembled interactively: (a) the key behavior restated as the primary outcome (from S1); (b) arms — each idea becomes at most one arm, each arm differs on one thing, plus a holdout (S17); (c) a calibrated effect-size prior with the optimistic/realistic/null-plausible range (S16); (d) the power section **explained twice in plain language** — frequentist: "this design detects a 3pp lift or larger; anything smaller will look like a null even if real" — and Bayesian: "given the prior, here's how each possible result should move your beliefs, and here's the probability the test ends decisively rather than ambiguously"; (e) a one-page pre-analysis plan with a stopping rule (S19); (f) a go/no-go verdict — including the honest "your sample can't answer this question; here's the cheaper proximal-outcome design that can."
5. **Where it goes wrong:** Scope creep back into "design my whole program" (the skill must insist on one behavior, one primary outcome); users treating the Bayesian readout as permission to peek and stop early; the walkthrough generating a beautiful plan for an idea that S2/S3 would have revealed to be aimed at the wrong barrier — it should ask "have you diagnosed?" before designing; false fluency — producing statistically polished plans whose delivery instrumentation (the silent killer, see S17/S20) was never checked.

---

# Ready to port — what IL can contribute *now*

Three assets exist in IL's internal skills system today and need only de-IL-ifying (stripping internal file paths, client references, and brand assumptions):

1. **`key-behavior` → S1.** A complete, battle-tested skill with mode detection (workshop facilitation vs direct definition vs critique of an existing key behavior) and the Impact/Drop-off/Control prioritization built in.
2. **`generate-psych-annotations` → "Behavioral Rationale Annotator."** Takes a design/solution and outputs mechanism-named "why this works" rationale. Needs its internal taxonomy dependency replaced with a public, citation-linked concept list — which this catalogue's reference list seeds.
3. **The skill-creation eval harness → the repo's QA backbone.** Test-prompt evals, variance benchmarking, and trigger-description optimization (P6/P7). Plus a repo skeleton — `skills/<name>/SKILL.md` + `references/` + `evals/` — so every skill installs directly into Claude Code/Cowork, AcademicForge-style ("pick, copy, run").

---

# Our proposed top 8 (for the vote)

| # | Skill | Why it's top-8 |
|---|-------|----------------|
| S1 | Key Behavior Definer | Already built; the upstream skill everything else depends on |
| S3 | COM-B Barrier Decomposer | The doc's own flagship example; canonical framework; unclaimed |
| S6 | Reminder Designer | Every org sends reminders; best LMIC evidence in the design stage; dosage guardrail is genuinely non-obvious |
| S8 | Social Norm Message Checker | The most-requested *and* most dangerous message type — guardrails earn their keep |
| S11 | Default & Friction Restructurer | Strongest evidence class in the toolkit; survives at scale |
| S16 | Effect Size Reality Checker | The calibration layer every other skill cites; prevents fantasy KPIs |
| S17 | Message A/B Test Designer | Testing is the foundational capability for non-specialists, and IL's deepest current practice |
| S18 | Power & MDE Calculator | The procedural complement to S17; cheap to build (script exists in our NH/RL work) |

*Honorable mentions:* S20 (Null Result Diagnostician — nobody else will propose it, and it encodes the most expensive lesson we've learned), S21 (Rapid Qual Pretest), and S22 (Experiment Design Walkthrough — if the group prefers fewer, bigger contributions, S22 subsumes S16–S19 as one guided skill and would be our single highest-value build).

## Full scoring matrix

| Skill | Stage | Org demand | Evidence strength | LMIC evidence | IL edge | Build effort |
|-------|-------|-----------|-------------------|---------------|---------|--------------|
| S1 Key Behavior Definer | Define | High | Methodological | Partial | **High (built)** | S |
| S2 Funnel Leak Finder | Define | High | Moderate | Yes | High | M |
| S3 COM-B Decomposer | Diagnose | High | Strong (framework) | Partial | Med | S |
| S4 Barrier Interview Guide | Diagnose | Med | Strong (method) | Partial | Med | S |
| S5 Cognitive Load Auditor | Diagnose | Med | Moderate (flagged) | Yes | Med | M |
| S6 Reminder Designer | Design | High | Strong | **Yes** | High | M |
| S7 Planning Prompt Builder | Design | Med | Strong (lab) / Mod (field) | Partial | Med | S |
| S8 Social Norm Checker | Design | High | Strong incl. backfire | Partial | Med | M |
| S9 Incentive Menu Designer | Design | Med | Strong | **Yes** | Med | M |
| S10 Commitment Designer | Design | Low-Med | Strong | **Yes** | Med | M |
| S11 Default Restructurer | Design | High | **Strongest** | Partial | Med | M |
| S12 Messenger Selector | Design | Med | Strong | **Yes** | **High (live test)** | M |
| S13 Fresh Start Picker | Design | Low | Fragile (flagged) | No | Low | S |
| S14 Values Affirmation | Design | Low | Fragile (flagged) | No | Low | S |
| S15 Generalizability Checker | Calibrate | Med | Strong | By design | Med | M |
| S16 Effect Size Reality Checker | Calibrate | High | **Strong, recent** | Partial | **High** | M |
| S17 A/B Test Designer | Test | High | Strong | Yes | **High (practice)** | M |
| S18 Power/MDE Calculator | Test | High | Strong | Yes | **High (scripts exist)** | S–M |
| S19 PAP Drafter | Test | Med | Strong | Yes | High | S |
| S20 Null Diagnostician | Test | Med | Moderate | Partial | **High (scar tissue)** | M |
| S21 Qual Pretest Designer | Test | Med | Strong (method) | Partial | Med | S |
| S22 Experiment Design Walkthrough | Test (molecule) | **High** | Strong | Yes | **High (practice + scripts)** | M–L |

---

# Collision map (against already-claimed skills)

| Claimed (by) | Our adjacent skill | Relationship |
|---|---|---|
| Cognitive interview script generator (Zezhen) | S4, S21 | His = survey-item pretesting; ours = barrier diagnosis / content pretesting. Cross-reference, don't merge. |
| Agency measurement helper (Zezhen) | — | No overlap. |
| Existing measure finder + psychometric development (Patricia) | S18, S19 | Hers = what to measure; ours = whether the test can detect it. Compose naturally. |
| Cultural psych lens (Patricia) | S15 | Hers audits the *design* via theory; ours audits the *evidence* via samples/scale. Cross-reference. |
| Pre-mortem analysis (Patricia) | S20 | Hers = before launch (prospective); ours = after a null (retrospective). Bookends. (Note for her draft: the premortem's empirical base is thin — Klein 2007 is an HBR practitioner piece, not peer-reviewed; the underlying "prospective hindsight" study is pre-2000.) |
| Intervention mapping + TPB message customizers (Kelly) | S6–S14 | Hers = framework-level message construction; ours = mechanism-level micro-skills that her frameworks can invoke. |

---

# Counterfactual check

Four ways this list could be wrong, stated plainly:

1. **We may be over-indexed on the i-frame.** Nearly everything above intervenes on individuals (messages, prompts, defaults) rather than systems. The strongest standing critique of applied behavioral science argues exactly this — that individual-level framing has distracted from systemic change (Chater & Loewenstein 2023, *Behavioral and Brain Sciences*). Counter-counter: defaults/friction (S11, S2) *are* small s-frame moves, and NGO program teams mostly control the i-frame levers. But the repo would be intellectually honest to include one skill we have *not* listed: a "systemic alternative checker" that asks, before any nudge, whether a structural fix would dominate.
2. **Maybe orgs don't want atoms — they want the molecule.** A PM under deadline may want "design my campaign," not eleven composable steps. We've partially conceded this point: S22 (Experiment Design Walkthrough) is exactly such a molecule for the test-and-learn chain, built *on top of* the atoms rather than instead of them. Whether more molecules are needed should be settled by usage data, not argument (see #4).
3. **Rigor could curdle into uselessness.** If every output is hedged ranges and caveats, the non-specialist user gets decision paralysis instead of overconfidence — trading one failure mode for another. Mitigation: every skill's output template ends with a single "if you only do one thing" line *after* the options. That line must survive editing.
4. **This list was generated from the literature and our practice, not from user demand.** The honest test of a skills repo for NGO teams is which skills NGO teams actually invoke. Proposal: before the group builds the top vote-getters, run our own S21 on the shortlist — 5–8 interviews with program staff at RL, Noora, and one non-TAF org, asking them to walk through last month's decisions and flag where a skill would have been invoked. Eat the dog food before cooking more of it.

---

# References (all verified; peer-reviewed journals unless flagged)

- Allcott, H. (2011). Social norms and energy conservation. *Journal of Public Economics*, 95(9–10), 1082–1095.
- Angrist, N., Bergman, P., & Matsheng, M. (2022). Experimental evidence on learning using low-tech when school is out. *Nature Human Behaviour*, 6, 941–950.
- Ashraf, N., Karlan, D., & Yin, W. (2006). Tying Odysseus to the mast: Evidence from a commitment savings product in the Philippines. *Quarterly Journal of Economics*, 121(2), 635–672.
- Banerjee, A., Chandrasekhar, A. G., Duflo, E., & Jackson, M. O. (2019). Using gossips to spread information: Theory and evidence from two randomized controlled trials. *Review of Economic Studies*, 86(6), 2453–2490.
- Banerjee, A. V., Duflo, E., Glennerster, R., & Kothari, D. (2010). Improving immunisation coverage in rural India. *BMJ*, 340, c2220.
- Beatty, P. C., & Willis, G. B. (2007). Research synthesis: The practice of cognitive interviewing. *Public Opinion Quarterly*, 71(2), 287–311.
- Bettinger, E. P., Long, B. T., Oreopoulos, P., & Sanbonmatsu, L. (2012). The role of application assistance and information in college decisions: Results from the H&R Block FAFSA experiment. *Quarterly Journal of Economics*, 127(3), 1205–1242.
- Bicchieri, C., & Dimant, E. (2022). Nudging with care: The risks and benefits of social information. *Public Choice*, 191, 443–464.
- Boateng, G. O., Neilands, T. B., Frongillo, E. A., Melgar-Quiñonez, H. R., & Young, S. L. (2018). Best practices for developing and validating scales for health, social, and behavioral research: A primer. *Frontiers in Public Health*, 6, 149.
- Braun, V., & Clarke, V. (2006). Using thematic analysis in psychology. *Qualitative Research in Psychology*, 3(2), 77–101.
- Bryan, C. J., Tipton, E., & Yeager, D. S. (2021). Behavioural science is unlikely to change the world without a heterogeneity revolution. *Nature Human Behaviour*, 5(8), 980–989.
- Casey, K., Glennerster, R., & Miguel, E. (2012). Reshaping institutions: Evidence on aid impacts using a preanalysis plan. *Quarterly Journal of Economics*, 127(4), 1755–1812.
- Chater, N., & Loewenstein, G. (2023). The i-frame and the s-frame: How focusing on individual-level solutions has led behavioral public policy astray. *Behavioral and Brain Sciences*, 46, e147.
- Cohen, G. L., Garcia, J., Apfel, N., & Master, A. (2006). Reducing the racial achievement gap: A social-psychological intervention. *Science*, 313(5791), 1307–1310.
- Cohen, G. L., & Sherman, D. K. (2014). The psychology of change: Self-affirmation and social psychological intervention. *Annual Review of Psychology*, 65, 333–371.
- Dai, H., Milkman, K. L., & Riis, J. (2014). The fresh start effect: Temporal landmarks motivate aspirational behavior. *Management Science*, 60(10), 2563–2582.
- Datta, S., & Mullainathan, S. (2014). Behavioral design: A new approach to development policy. *Review of Income and Wealth*, 60(1), 7–35.
- DellaVigna, S., & Linos, E. (2022). RCTs to scale: Comprehensive evidence from two nudge units. *Econometrica*, 90(1), 81–116.
- Gelman, A., & Carlin, J. (2014). Beyond power calculations: Assessing Type S (sign) and Type M (magnitude) errors. *Perspectives on Psychological Science*, 9(6), 641–651.
- Gallagher, K. M., & Updegraff, J. A. (2012). Health message framing effects on attitudes, intentions, and behavior: A meta-analytic review. *Annals of Behavioral Medicine*, 43(1), 101–116.
- Gerber, A. S., Green, D. P., & Larimer, C. W. (2008). Social pressure and voter turnout: Evidence from a large-scale field experiment. *American Political Science Review*, 102(1), 33–48.
- Giné, X., Karlan, D., & Zinman, J. (2010). Put your money where your butt is: A commitment contract for smoking cessation. *American Economic Journal: Applied Economics*, 2(4), 213–235.
- Gneezy, U., Meier, S., & Rey-Biel, P. (2011). When and why incentives (don't) work to modify behavior. *Journal of Economic Perspectives*, 25(4), 191–210. *(Invited review.)*
- Gollwitzer, P. M., & Sheeran, P. (2006). Implementation intentions and goal achievement: A meta-analysis of effects and processes. *Advances in Experimental Social Psychology*, 38, 69–119. *(Book-series chapter.)*
- Hanselman, P., Rozek, C. S., Grigg, J., & Borman, G. D. (2017). New evidence on self-affirmation effects and theorized sources of heterogeneity from large-scale replications. *Journal of Educational Psychology*, 109(3), 405–424.
- Henrich, J., Heine, S. J., & Norenzayan, A. (2010). The weirdest people in the world? *Behavioral and Brain Sciences*, 33(2–3), 61–83.
- Jachimowicz, J. M., Duncan, S., Weber, E. U., & Johnson, E. J. (2019). When and why defaults influence decisions: A meta-analysis of default effects. *Behavioural Public Policy*, 3(2), 159–186.
- Johnson, E. J., & Goldstein, D. (2003). Do defaults save lives? *Science*, 302(5649), 1338–1339. *(Policy Forum.)*
- Karlan, D., McConnell, M., Mullainathan, S., & Zinman, J. (2016). Getting to the top of mind: How reminders increase saving. *Management Science*, 62(12), 3393–3411.
- Kruschke, J. K., & Liddell, T. M. (2018). The Bayesian New Statistics: Hypothesis testing, estimation, meta-analysis, and power analysis from a Bayesian perspective. *Psychonomic Bulletin & Review*, 25(1), 178–206.
- Kremer, M., Rao, G., & Schilbach, F. (2019). Behavioral development economics. In *Handbook of Behavioral Economics: Foundations and Applications 2*. Elsevier. *(Handbook chapter.)*
- Maier, M., Bartoš, F., Stanley, T. D., Shanks, D. R., Harris, A. J. L., & Wagenmakers, E.-J. (2022). No evidence for nudging after adjusting for publication bias. *PNAS*, 119(31), e2200300119.
- Mani, A., Mullainathan, S., Shafir, E., & Zhao, J. (2013). Poverty impedes cognitive function. *Science*, 341(6149), 976–980. *(Published critique: Wicherts & Scholten 2013; mixed conceptual replications.)*
- McKenzie, D. (2012). Beyond baseline and follow-up: The case for more T in experiments. *Journal of Development Economics*, 99(2), 210–221.
- Mertens, S., Herberz, M., Hahnel, U. J. J., & Brosch, T. (2022). The effectiveness of nudging: A meta-analysis of choice architecture interventions across behavioral domains. *PNAS*, 119(1), e2107346118. *(See published correction and Maier et al. critique.)*
- Michie, S., Richardson, M., Johnston, M., et al. (2013). The Behavior Change Technique Taxonomy (v1) of 93 hierarchically clustered techniques. *Annals of Behavioral Medicine*, 46(1), 81–95.
- Michie, S., van Stralen, M. M., & West, R. (2011). The behaviour change wheel: A new method for characterising and designing behaviour change interventions. *Implementation Science*, 6, 42.
- Milkman, K. L., Beshears, J., Choi, J. J., Laibson, D., & Madrian, B. C. (2011). Using implementation intentions prompts to enhance influenza vaccination rates. *PNAS*, 108(26), 10415–10420.
- Milkman, K. L., et al. (2021). A megastudy of text-based nudges encouraging patients to get vaccinated at an upcoming doctor's appointment. *PNAS*, 118(20), e2101165118.
- Milkman, K. L., et al. (2021). Megastudies improve the impact of applied behavioural science. *Nature*, 600, 478–483.
- Nickerson, D. W., & Rogers, T. (2010). Do you have a voting plan? Implementation intentions, voter turnout, and organic plan making. *Psychological Science*, 21(2), 194–199.
- Olken, B. A. (2015). Promises and perils of pre-analysis plans. *Journal of Economic Perspectives*, 29(3), 61–80. *(Solicited review.)*
- Pop-Eleches, C., et al. (2011). Mobile phone technologies improve adherence to antiretroviral treatment in a resource-limited setting: A randomized controlled trial of text message reminders. *AIDS*, 25(6), 825–834.
- Schultz, P. W., Nolan, J. M., Cialdini, R. B., Goldstein, N. J., & Griskevicius, V. (2007). The constructive, destructive, and reconstructive power of social norms. *Psychological Science*, 18(5), 429–434.
- Shah, A. K., Mullainathan, S., & Shafir, E. (2012). Some consequences of having too little. *Science*, 338(6107), 682–685.
