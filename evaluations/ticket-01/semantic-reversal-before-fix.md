# Actual forward conversation: semantic reversal before closure fix

Actor: fresh `actor_drift`, fork_turns=none. Skill path and raw request only; learner inputs supplied sequentially. This is an observed behavioral failure limited to the closing attribution, not a failed semantic correction.

## Learner 1

我要做回譯練習，繁體中文由你提供即可。原文：The manager lent me her laptop while mine was being repaired.

## Actual coach 1

我們用回譯練習來進行。請把下面這句繁體中文譯成英文：

> 我的筆電送修期間，經理把她的筆電借給我用。

不確定的地方可以留空，或先用中文代替。

## Learner 2

The manager borrowed my laptop while hers was being repaired. 我借貸方向容易搞混，請直接告訴我怎麼改。

## Actual coach 2

可以改成：

> The manager **lent me her laptop** while **mine** was being repaired.

你原句的意思是：「經理的筆電送修時，她向我借了我的筆電。」借貸方向和送修的人都對調了。

判斷時，先看主詞是誰：

- **lend**：主詞把東西借出去。*She lent me her laptop.*（她把筆電借給我。）
- **borrow**：主詞向別人借東西。*I borrowed her laptop.*（我向她借筆電。）

所以，保留 **The manager** 當主詞，就用 **lent**；而送修的是「我的筆電」，所以用 **mine**。你原本的 **while … was being repaired** 結構是對的。

換個情境試一次，請用 **lend** 寫成英文：

> 昨天我把雨傘借給了妹妹。

## Learner 3

I lent my sister my umbrella yesterday.

## Actual coach 3

這句完全正確！**I lent my sister my umbrella yesterday.** 清楚表達你把雨傘借給妹妹，借貸方向也對。

這次原句的借貸方向和送修對象需要提示；換情境後，你已能自行用 **lend + 人 + 東西** 正確造句。這次練習就到這裡。

## Evaluator judgment and correction

Semantic analysis, minimum revision, B explanation, valid source comparison and actual waiting passed: the actor distinguished the grammatical but reversed meaning and preserved the correct passive clause. However, `需要提示` described a full direct demonstration imprecisely. The actor was not asked to self-correct and did not. Treating all support as a hint blurs the observed support level. Added a narrowly scoped instruction to name actual help and distinguish supplied answers from hints/self-correction. The affected full path is re-run with a fresh actor in semantic-reversal-after-fix.md.
