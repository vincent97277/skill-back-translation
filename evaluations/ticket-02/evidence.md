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
