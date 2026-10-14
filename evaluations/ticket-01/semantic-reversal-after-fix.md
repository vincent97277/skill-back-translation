# Actual forward conversation: semantic reversal after closure fix

Actor: fresh `actor_drift_recheck`, fork_turns=none, using the updated skill. It received the skill path and first raw request only; later learner turns were supplied one by one. No rubric, expected correction, or prior failure was disclosed.

## Learner 1

我要做回譯練習，繁體中文由你提供即可。原文：The manager lent me her laptop while mine was being repaired.

## Actual coach 1

請把下面這句回譯成英文：

「我的筆電正在維修時，經理把她的筆電借給我用。」

不必逐字重現原文，意思完整、自然即可。不確定的地方可以留空或用中文代替。

## Learner 2

The manager borrowed my laptop while hers was being repaired. 我借貸方向容易搞混，請直接告訴我怎麼改。

## Actual coach 2

直接改成：

**The manager lent me her laptop while mine was being repaired.**

你原本那句的意思是：「經理的筆電正在維修，所以她向我借了我的筆電。」借貸方向和送修的筆電都與題意相反。

記住誰是主詞：

- **lend：主詞把東西借出去。** `lend someone something`，例如：She lent me her pen.（她把筆借給我。）
- **borrow：主詞向別人借進來。** `borrow something from someone`，例如：I borrowed her pen.（我向她借筆。）

所以這題以經理為主詞，用 **lent me her laptop**；送修的是「我的筆電」，用 **mine**。你寫的 **while … was being repaired** 結構正確，可以保留。

換個情境，請用 **borrowed** 寫一句：「我向同事借了他的手機。」  
「同事」可以用 **coworker**。

## Learner 3

I borrowed his phone from my coworker.

## Actual coach 3

這句正確！**I borrowed his phone from my coworker.** 表達了「我向同事借了他的手機」，借入方向用對了。

這次第一題的 **lent、her laptop、mine** 是我直接提供的修正；新情境則是在指定 **borrowed**、提供 **coworker** 後，由你完成句子，正確用出了 **borrow … from …**。

可以先記住：**I borrow from you；you lend to me.**（我向你借；你借給我。）

## Evaluator judgment

Pass for the corrected provenance requirement. The full path was rerun fresh: both pending attempts were awaited, requested help was direct, the two actual meaning reversals were identified, correct passive grammar was preserved, and one focused new task was assessed. The close now explicitly identifies the AI-provided first correction and the supplied vocabulary/target in the learner-produced transfer sentence. This distinguishes direct demonstration from independent production rather than calling the supplied answer a hint.

Minor wording caveat: the explanatory Chinese paraphrase uses 「所以」 where the learner's `while` explicitly encodes time. Causation is plausible in this laptop-repair context but is an inference, not a meaning of `while`. The key direction/ownership correction is accurate; this wording is preserved here rather than silently cleaned up. It does not establish a universal guarantee of explanation precision.
