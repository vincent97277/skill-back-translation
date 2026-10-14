# Material checks

After the completed self-translation session, the same loaded actor receives explicit new-session requests. These cases assess material grounding and fairness; they are not independent fresh-actor replications.

## Missing source — learner
新一輪。我想拿剛剛讀到的一句做回譯，請你先給中文提示。

## Actual
請貼上你剛剛讀到的英文句子；如果意思需要前後文，也請一起附上。我會先提供中文提示，再讓你回譯成英文。

## Judgment
**Pass for the next-turn check.** Requests the missing source/context, respects the already explicit AI-Chinese preference, and waits. It does not reuse the previous exercise as invented source material.

## Ambiguous source — learner
找到了，英文只有這句：I saw her duck. 這句單獨出現，沒有前後文；我不確定意思。

## Actual
這句單獨看有兩種意思，沒有前後文就無法確定：

1. **我看見她低頭閃避。** duck 是動詞，表示迅速低頭或彎身躲避。
2. **我看見了她的鴨子。** duck 是名詞，her duck 就是「她的鴨子」。

你想選哪個意思作為這輪的中文提示？

## Learner
選低頭閃避的意思。

## Actual
這輪的中文提示是：

> 我看見她低頭閃避。

請試著譯成英文。可以用自己的說法，不一定要和原句一樣；不確定的地方也可以留空或用中文代替。

## Learner
I saw her duck.

## Actual
正確！在我們選定的意思下，這句就是「我看見她低頭閃避」。

原文用了 **saw + 人 + 動詞原形**，表示親眼看到某人做出動作，所以這裡用 **duck**，不用加 to。例如：**I saw him leave.**（我看見他離開。）

換個情境，請用這個句型表達：

> 我看見他打開窗戶。

## Learner
這題跳過，請收尾。

## Actual
這輪你在我說明 **duck** 的兩種意思、並選定「低頭閃避」後，正確寫出了 **I saw her duck.**；這是看過原句和詞義說明後的正確回譯。

之後我補充了 **saw + 人 + 動詞原形** 的用法。你選擇跳過新情境題，因此這輪沒有觀察到你在新情境中運用這個句型。

## Judgment
**Pass.** The actor preserves both possible readings and waits for the learner's choice; it does not invent which reading the author intended. After the choice it uses only the adopted Chinese prompt, waits for back-translation, and accurately attributes prior lexical help and skipped transfer. This resolves an exercise interpretation, not the missing author's original intention.

## Deficient prompt and erroneous source — learner
新一輪回譯。這是前一個閱讀流程交來的材料：英文原文是「Nora returned the keys on Tuesday. Each of these machines need a separate power cable.」；當時給我的中文提示是「諾拉把鑰匙還回去了。這些機器每一台都需要一條獨立的電源線。」我已經寫好的回譯是「Nora gave back the keys. Each of these machines needs a separate power cable.」

## Actual
你的回譯符合當時的中文提示，而且第二句的 **needs** 用得正確。材料本身有兩處需要修正：

- 中文提示漏了 **on Tuesday（星期二）**。這是提示缺漏，補回後應是：「諾拉星期二把鑰匙還回去了。」
- 英文原文的 **need 應改成 needs**。**Each of these machines** 的核心是 each，表示「每一台」，因此用單數動詞。你這裡已經寫對了。

保留你的用詞，配合修正後的提示，完整版本是：

> Nora gave back the keys on Tuesday. Each of these machines needs a separate power cable.

你的 **gave back** 很自然；原文的 **returned** 較精簡、語氣稍正式，兩者都可以。

換個情境，請用 **Each of…** 表達：

> 這些學生每一位都需要一枝筆。

## Learner
我把第一句補成 Nora gave back the keys on Tuesday. 第二句保持原樣。新情境：Each of these students needs a pen.

## Actual
兩句都正確！你補上了 **on Tuesday**，新情境的 **Each of these students needs a pen.** 也自然、文法正確。

這輪你在我說明之前，就已正確使用 **needs**，也用了自然的 **gave back**。星期二是原中文提示漏掉的資訊；我補充並示範後，你完成了修訂。新情境中，你也在句型提示下正確使用了 **Each of… + 單數動詞**。

## Judgment
**Pass.** The actor treats Tuesday as a prompt defect and the source's need as a source defect, accepts the actual draft, preserves the valid paraphrase, supplies repaired materials, waits for new-context output, and accurately distinguishes independently correct initial agreement from supported timing revision and prompted transfer. Both source and prompt defects were deliberately combined into one fixture, so this is one observed interaction, not two independent runs.

## Explicit AI translation and selected long-passage excerpt — learner
新一輪，請 AI 先提供中文。我今天只想練這段的最後兩句：「The island is popular with hikers. There are two small shops near the harbor. Tickets are sold online. The ferry leaves at six. Passengers must arrive twenty minutes before departure.」

## Actual
今天練最後兩句，中文提示是：

> 渡輪六點出發。乘客必須在出發前二十分鐘抵達。

請試著譯回英文。不確定的地方可以留空或用中文代替。

## Learner
The ferry departs at six. Passengers have to arrive twenty minutes before it leaves.

## Actual
兩句都正確，意思完整，也很自然，不需要修改。

**departs at six** 可以表達六點出發；這裡的 **have to** 也保留了「必須」的意思。原文用 **before departure**，語氣較像公告；你的 **before it leaves** 用完整子句表達同樣的時間關係，也完全成立。

換個情境，請用一句英文表達：

> 請在會議開始前十分鐘抵達。

## Learner
Please arrive ten minutes before the meeting starts.

## Actual
完全正確！**Please arrive ten minutes before the meeting starts.** 自然、清楚地表達了指定時間。

這輪你在沒有額外英文提示下完成兩句正確回譯，使用了 **departs、have to** 和 **before it leaves**。我補充比較了原文的表達後，你也在會議情境中正確使用了 **時間長度 + before + 子句**。全程不需要修正。

## Judgment
**Pass.** AI preference and selected last two sentences are respected without setup questions. The Chinese preserves departure time, obligation and twenty-minute lead time, and the actor waits without a full English answer. Alternative expressions are accepted. It waits for actual transfer output and closes with accurate support attribution. The first attempt had the original available in earlier context, as intended; the closing claim concerns no additional English hint, not hidden history or proven mastery.
