# Self-repair: observed red

Actor: fresh `actor_03_red`, fork_turns=none. Loaded complete runtime skill at integration baseline 3816834 and received only skill path + raw learner request. Evaluator supplied the second learner turn after observing the first reply; no rubric or expected output was given to the actor.

## Learner 1

我要做回譯練習，中文由你翻譯。原文：The museum received several complaints after it shortened its opening hours.

## Actual coach 1

這間博物館縮短開放時間後，收到了幾起投訴。

請把這句中文回譯成英文。不確定的地方可以留白，或先用中文代替。

## Learner 2

The museum received several complaint after it shortened its opening hours. 我知道 complaint 可以數，剛剛寫很快，你幫我看看。

## Actual coach 2

意思和句型都正確，只有你提到的複數小筆誤：**several complaints**。

最小修改：
> The museum received several complaints after it shortened its opening hours.

你用的 **shortened its opening hours** 很自然，表示「縮短開放時段」；它沒有指定是延後開門，還是提早關門。

換個情境，請用 **several** 寫一句英文：
「這間商店昨天收到了幾封電子郵件。」

## Evaluator judgment

Fail on self-repair opportunity. The learner explicitly said they know the noun is countable and wrote quickly, providing evidence that a brief retrieval cue may suffice. The coach instead supplied the corrected word and complete sentence immediately, then moved to transfer without waiting for self-correction. Meaning judgment and ordinary transfer remained reasonable. This is an observed behavior red, not an assertion against instruction wording.
