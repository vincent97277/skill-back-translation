# Ticket 02 evaluation

## Boundary and red

The pre-agreed seam is the actual user-visible conversation after loading the complete skill. Actors receive only the skill path and raw task; expected criteria stay with the evaluator. Learner fixtures are supplied in separate turns. No static prose matching is used as a behavioral test.

The baseline skill at integration commit `3816834` was loaded by a fresh actor with this request:

> 我想做回譯練習。英文是：The library will remain closed until the repairs are complete.

Actual next message:

```text
請把這句中文譯回英文：

「圖書館在修繕工程完成前會持續閉館。」

用你自己的說法就好，不必逐字重現原句。遇到不會的地方，可以留空或用中文代替。
```

Expected: offer learner Chinese translation or AI translation and wait, since no preference was given. Observed: immediately supplied Chinese and asked for English. **Fail (red).** The translation itself is reasonable; the missing choice is the failure.

## Expected behavior for the next slice

Use a learner translation with a timing/condition misunderstanding: explain the meaning contrast, repair the Chinese, wait for an actual English attempt, and complete the shared transfer/closure path. Later reuse of a structure already taught in Chinese feedback must be attributed as supported. Also observe missing source, materially ambiguous context, a deficient Chinese prompt, a confirmable source error, and the existing explicit-AI path. Judgments assess meaning, material fairness and waiting, rather than matching wording.

## Scope of evidence

These are controlled model conversations, not human learning trials or evidence of long-term mastery. Packaging validation is separate from behavior.

## Observed green results

- [Self-translation transcript](self-translation.md): the same baseline request now receives choice/wait; Chinese meaning reversal receives B feedback; repaired prompt leads directly to actual English, valid alternative acceptance, one supported transfer and accurate close.
- [Material transcripts](materials.md): missing-source wait; genuine ambiguity preserved until learner chooses an exercise reading; prompt timing omission accepted and repaired; confirmable source agreement error repaired while preserving the learner's correct version; both material repairs followed by actual revision/transfer and close; explicit AI translation of a user-selected two-sentence excerpt retains the existing wait/alternative/transfer behavior.

No additional semantic failure was observed in these green fixtures. The baseline preference failure remains recorded above. The green actor loaded the complete changed skill fresh once; later cases explicitly start new sessions inside that actor. They test multiple paths but are not independent repeated trials. The omission and source-error defects share one supplied fixture. The material-defect fixture enters with an actual evaluator-supplied draft, so it tests repair and follow-through rather than reproducing initial prompt creation.

## Structure checks

The bundled quick validator, run using `/private/tmp/back-translation-validation/bin/python`, reported **Skill is valid!**. No runtime dependency or supporting reference was needed for this short branch addition. `git diff --check integration/back-translation-skill...HEAD` passed after the initial implementation commit; final integration checks are recorded at completion.

## Coverage limits

These finite fixtures cover representative semantic reversal, timing omission, obvious agreement error and a lexical/syntactic ambiguity. They do not exhaust negation, condition, register or all source-quality judgments. The long-passage fixture honors an explicit selection; autonomous excerpt selection is instructed but not independently sampled here. Installed automatic discovery, human learning gains, retention and cross-chat transfer remain untested. Runtime instructions do not depend on these evaluation records or this repo's design history.
