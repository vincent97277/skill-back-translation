# Ticket 04 integrated evaluation

## Boundary and evaluator criteria

The agreed boundary remains the user-visible conversation after loading the complete runtime skill. Fresh actors receive the skill path plus raw learner tasks, with learner fixtures supplied sequentially after actual coach outputs. Expected criteria, earlier outputs and failure diagnoses remain evaluator-side. Actors do not author their own learner replies. Runtime at `990d892` combines tickets 01–03; the latest integration documentation update does not change that runtime.

Criteria for the handoff slices: source-only entry must select an appropriately small, complete excerpt and preserve an unspecified translation choice; adopted Chinese/no attempt must proceed to English production and wait; an actual draft must be reused for feedback; an existing self-repair cue must remain pending until an actual answer/help/skip; deficient handoff materials must be repaired before assigning errors. Completion/end must close accurately and resume the requested surrounding task using actual available evidence. All use the same correction/fairness/alternative/depth rules and require no external service or saved profile.

The baseline observations passed their sampled states: [actual draft with deficient prompt](handoff-baseline.md) and [adopted Chinese plus pending hint/direct-answer request](resume-states.md). No behavioral red was observed in these baselines, and no runtime change is claimed as a red-to-green fix. Ticket 04 completes additional observable coverage and first-version delivery documentation rather than adding a duplicate instruction for behavior that already passed. TDD's existing red/green corrections remain documented under tickets 01–03.

## Observed integrated behavior

- [Source-only reading entry](source-entry.md): fresh actor, autonomous two-sentence selection from a seven-sentence passage, translation choice/wait, learner-Chinese repair, actual English with placeholder/direct help, valid alternatives, requested structural explanation, one supported transfer, requested shortening/end and substantive reading return. This fills the prior autonomous-excerpt-selection sampling gap.
- [Adopted Chinese and pending self-repair](resume-states.md): one fresh actor with two explicitly separate sessions. Checked Chinese goes straight to production; an unresolved cue stays unresolved until direct help, then transfer can be skipped and the original reading question resumed. This is not two independent actor repeats.
- [Actual draft plus deficient handoff prompt](handoff-baseline.md): separate fresh actor, prompt omission repaired before assessment, fair draft acceptance, observed supported transfer and return; missing surrounding report material is requested rather than fabricated.
- [Ordinary grammar/rewrite](ordinary-requests.md): a separate fresh actor per task, ordinary purpose retained after explicitly loading the runtime. One grammar attempt hit a usage limit and was retried without a prior useful output. Installation/discovery is outside these observations.

## Whole-spec coverage index

The integrated runtime is unchanged from the combined tickets 01–03. Earlier evidence is retained at its actual observation point, not described as rerun here. Ticket 02 and ticket 03 notes explain which earlier cases predate their last integration merge. Ticket 04 fresh actors all read the complete combined runtime. The index groups observable stories; coverage is representative rather than an exhaustive proof for all possible inputs.

| User stories | Behavior and actual evidence |
| --- | --- |
| 1–3, 41–42 | Explicit practice, ordinary requests and surrounding-task entry/return: the ticket 04 transcripts above, plus [ticket 01 ordinary translation](../ticket-01/ordinary-translation.md). |
| 4–6 | Missing source and material ambiguity: [ticket 02 materials](../ticket-02/materials.md); automatic short excerpt selection: [source entry](source-entry.md). |
| 7–12 | Both Chinese paths, preference reuse, repair and actual-attempt waits: [ticket 02 self-translation](../ticket-02/self-translation.md), [ticket 02 explicit-AI/materials](../ticket-02/materials.md), [source entry](source-entry.md), [adopted Chinese](resume-states.md). |
| 13–17 | Placeholder/direct support, self-repair cue and wait, actual successful repair, help after failed retrieval: [ticket 03 self-repair green](../ticket-03/self-repair-green.md), [ticket 03 demonstration/early end](../ticket-03/direct-demo-and-early-end.md), [pending cue](resume-states.md), [source entry](source-entry.md). |
| 18–26 | Meaning impact, minimal correction, valid alternatives, prompt/source fairness: [ticket 01 semantic rerun](../ticket-01/semantic-reversal-after-fix.md), [ticket 02 materials](../ticket-02/materials.md), [handoff material repair](handoff-baseline.md), [source entry](source-entry.md). |
| 27–34 | Default B contrast/rule/examples and requested C: [ticket 03 merged-runtime B-to-C](../ticket-03/b-to-c-green.md); A/shortening and practical activity adjustment: [ticket 03 self-repair](../ticket-03/self-repair-green.md), [demonstration/early end](../ticket-03/direct-demo-and-early-end.md), [source entry](source-entry.md). Source comparison accepts usable alternatives in the ticket 04 cases. |
| 35–40 | Actual new-context input and feedback, support, skip/end, accurate attribution and no required saved record: [ticket 03 green sessions](../ticket-03/evidence.md), all three ticket 04 practice transcripts. |
| 43–46 | Single-file self-contained runtime, structural validation, fresh-material loaded conversations and scoped load/install instructions: this record and [README](../../README.md). |

## Delivery, structure and integration

The delivered runtime folder contains only `skills/back-translation-practice/SKILL.md`. It has no supporting-file references, scripts, account dependencies, or dependency on the evaluation/design history. The README now points to the actual artifact, explains direct loading and optional local installation without performing it, and separates runtime files from research, prototypes and observed evaluations. Local discovery locations were checked against [official OpenAI documentation](https://learn.chatgpt.com/docs/build-skills) on 2026-10-15; older evaluation notes describe their original environment and do not supersede the current README guidance.

No installation, publication, push, persistent learner storage, scheduling or cross-chat messaging was performed. Contextual handoff remains same-conversation continuity. The parent spec is left for the root's final review and closure.

## Limits

These are finite model-actor fixture conversations with evaluator-supplied learner turns. They observe instruction following and meaningful waits, not human learning, timed session duration, long-term retention, proficiency or oral fluency. Materials are fresh for their actors, but several sessions share an actor where explicitly stated. Existing prior-ticket semantic and structural caveats remain in their evidence records. Different model runs may vary.

Autonomous excerpt selection and standalone grammar/rewrite response behavior now have loaded-runtime samples. Automatic skill discovery, selector UI, installation and an otherwise empty host without other installed English skills were not exercised. Self-containment is established by the package's absence of runtime dependencies and successful supplied-material conversations, not by claiming a clean-host installation trial. Semantic ambiguity, source quality and register judgments remain representative samples, not exhaustive linguistic validation.


## Final checks

- Merged latest integration `ee958ac76016e4ce7e992dca8e95a51266acd84a` before finalization; it changes ticket-breakdown documentation only.
- `/private/tmp/back-translation-validation/bin/python /Users/vincentlin/.codex/skills/.system/skill-creator/scripts/quick_validate.py skills/back-translation-practice` returned **Skill is valid!** on the merged tree.
- `git diff --exit-code integration/back-translation-skill -- skills/back-translation-practice/SKILL.md` returned 0: no runtime delta was retained in ticket 04.
- `git diff --check` passed; local README and ticket 04 evidence links resolve. Structure/link checks are delivery checks, not behavioral proxies.
- The staged whole-branch whitespace check first flagged Markdown hard-break spaces in copied coach outputs. Those trailing spaces were normalized without changing transcript wording; final whole-branch checks below supersede that packaging failure.
- Final committed whole-branch `git diff --check main...HEAD` passed; the ticket branch worktree was clean after commit.
