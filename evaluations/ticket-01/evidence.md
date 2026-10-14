# Ticket 01 evaluation

## Boundary and first red

Confirmed boundary: user-visible conversation after loading the complete skill. Actor agents receive only the skill location and raw learner requests; expected behavior stays in these evaluation notes. Fixture learner turns are supplied sequentially by the evaluator, never invented by the actor.

Before implementation, `test -f skills/back-translation-practice/SKILL.md` in this worktree exited **1** (2026-10-15). This is an observed missing-entrypoint red, not evidence of a semantic failure. The first slice creates the loadable AI-Chinese session and evaluates actual conversations next.

## Loading

The runtime package is `skills/back-translation-practice`. To try the checked-out copy, ask the agent to read that folder's SKILL.md and run the exercise. For normal discovery, explicitly install/copy that folder into the personal skills directory in a separate authorized installation task. This work does not install it or change personal settings. The runtime file has no dependency on this repository's design documents or evaluation records.

## Interpretation

These controlled conversations check observable instruction following with supplied learner fixtures. They do not measure human learning outcomes, long-term retention, or discovery performance in a live installed environment. Structural validation is reported separately from dialogue behavior.

## Observed results

- Valid alternative and completed transfer: [actual transcript](valid-alternative.md), passed.
- Plain translation boundary: [actual output](ordinary-translation.md), passed for this request.
- Chinese placeholder, direct help, and skipped transfer: [actual transcript](placeholder-and-skip.md), passed.
- Meaning reversal and B feedback: [first actual trace](semantic-reversal-before-fix.md) correctly explained the meaning but misnamed a direct demonstration as a hint at closure. A one-sentence provenance clarification was added.
- Fresh full-path rerun: [actual transcript](semantic-reversal-after-fix.md), corrected closing attribution passed. Minor contextual-causation wording caveat is recorded in that file.

## Structure checks

The system Python initially could not run the bundled validator because PyYAML was absent. With the separately provisioned temporary validator interpreter, `quick_validate.py skills/back-translation-practice` reported **Skill is valid!** before and after the correction. No runtime dependency was added to the skill. `git diff --check` passed. The single runtime entrypoint has no outbound reference links to resolve, no unfinished scaffolding, and no evaluation/design dependencies.

## Coverage and limits

The core AI-Chinese path, waiting, semantic meaning correction with B contrast, valid paraphrase, direct help, new-context response, and skip/accurate close have direct observed examples above. Normal translation remained translation in a separate fresh agent. UI discovery, installation and unrelated grammar/rewrite requests were not exercised in a live installed host. Self-translation, prompt/source repair, hint-first self-correction, A/C adaptation and surrounding-workflow handoff remain for their dedicated tickets. These are model-agent fixture conversations, not trials with human learners.
