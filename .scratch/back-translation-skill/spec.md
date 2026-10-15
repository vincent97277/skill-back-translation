# 回譯英文練習 skill：實作規格

Status: closed
Labels: ready-for-agent
Version: 1.0
Date: 2026-10-15

## Problem Statement

使用者希望把閱讀時看得懂的英文，轉成自己能寫出、未來能主動運用的表達。目前已完成回譯教學研究、流程設計與範例比較，但尚無可載入、重複使用的 skill。每次重新描述教學規則，容易造成回饋深度與錯誤判斷不一致，也不便在文章閱讀或其他英文流程中插入短練習。

實作需要忠實承載已確認的教學決策：以繁中提示促成英文產出，接受合理替代表達，分清材料問題與學習者問題，提供適量提示與解釋，並安排一次新情境運用。單有一份設計文件，尚不能證明載入後的實際對話會遵守這些決策。

## Solution

製作一個可供本機載入與後續安裝的回譯英文練習 skill，使用一套教學核心，支援獨立啟動及其他流程交接。成品先保留於目前專案，供檢查與試用；本次實作完成的定義不包含自動安裝到個人環境或公開發布。

預設每次使用一至三句英文，以約十分鐘的文字互動完成：理解原文、選擇自行英翻中或由 AI 提供中文、學習者回譯、必要支援與修訂、原文比較，以及新情境產出。使用者可以縮短、求助、調整深度或結束。

回饋以 B「理解對比」為主，需要時展開 C「結構與延伸」，只需提醒時縮為 A「精簡修正」。預設深入講解一至三個高價值重點，依實際答案略過空階段，不要求原文字面還原。

本版只提供單次練習，不依賴長期學習紀錄、外部題庫或服務。完成時如實總結當輪表現，不要求使用者保存摘要才能使用。

## User Stories

1. As an English learner, I want to explicitly request back-translation practice with an English passage, so that I can begin a focused learning session.
2. As an English learner, I want an ordinary translation or grammar question to retain its original purpose, so that unrelated requests do not unexpectedly become exercises.
3. As a learner already in a reading workflow, I want to practice selected sentences using the same teaching rules, so that I can apply the method without restarting the whole workflow.
4. As an English learner, I want a request for the missing original when it is required, so that feedback is grounded in real material.
5. As an English learner, I want short, contextually complete excerpts from longer passages, so that the exercise stays manageable without distorting meaning.
6. As an English learner, I want meaningful ambiguity clarified, so that the exercise does not depend on an invented interpretation.
7. As an English learner, I want to choose whether to translate the original into Traditional Chinese myself, so that I can decide whether to practice comprehension as well as production.
8. As an English learner, I want an already stated translation preference to be respected, so that I do not repeatedly answer setup questions.
9. As an English learner translating into Chinese, I want important misunderstandings corrected and explained, so that I do not practice from a mistaken meaning.
10. As an English learner, I want an accurate and natural Chinese prompt, so that I can express the intended meaning without being led by copied English syntax.
11. As an English learner, I want the accepted Chinese prompt presented without the full English answer during my attempt, so that I can try producing English myself.
12. As an English learner, I want the coach to wait for my actual answer, so that my work is not replaced by an invented learner response.
13. As an English learner, I want to leave gaps or use Chinese placeholders, so that I can still attempt a sentence when I lack part of the English.
14. As an English learner, I want direct help when I ask for it, so that I can continue without an endless guessing exercise.
15. As an English learner, I want one useful hint when I may be able to self-correct, so that I can retrieve what I know before seeing a complete revision.
16. As an English learner, I want a direct demonstration if a hint does not help, so that support remains proportionate to my difficulty.
17. As an English learner, I want the full corrected answer withheld while a self-correction prompt is still open, so that the attempt remains meaningful.
18. As an English learner, I want errors that reverse or obscure the key meaning addressed first, so that I learn to communicate the intended message.
19. As an English learner, I want the coach to explain what my sentence actually says, so that I understand a semantic difference even when my grammar is correct.
20. As an English learner, I want error type and impact treated separately, so that minor form issues and major meaning changes receive suitable attention.
21. As an English learner, I want each issue explained once, so that overlapping categories do not produce repetitive correction.
22. As an English learner, I want a complete revision that preserves my intent, so that I can see a usable version of my own expression.
23. As an English learner, I want correct wording retained, so that optional stylistic changes are not presented as necessary corrections.
24. As an English learner, I want valid alternatives accepted even when they differ from the original, so that success is not measured by copying the source.
25. As an English learner, I want missing or misleading Chinese information repaired, so that material defects are not attributed to my ability.
26. As an English learner, I want an inaccurate original corrected when necessary, so that I do not learn an error merely because it appears in the source.
27. As an English learner, I want a small number of valuable points explained deeply, so that I can understand the reasons without being overwhelmed.
28. As an English learner, I want B-level feedback to give a meaning contrast, a usage decision rule, and a useful short example, so that I can apply the distinction again.
29. As an English learner, I want a structural explanation when I ask why or remain confused, so that I can connect the example to a reusable pattern.
30. As an English learner, I want shorter feedback when I need a reminder or have limited time, so that I can control the pace.
31. As an English learner, I want irrelevant correction stages omitted, so that a correct answer receives clear and proportionate feedback.
32. As an English learner, I want specific suggestions for adding, combining, or shortening an activity, so that the lesson can adapt to an actual difficulty.
33. As an English learner, I want a session to continue without repeated configuration questions, so that adjustments do not interrupt ordinary practice.
34. As an English learner, I want source expressions compared in terms of meaning, register, or effect, so that I can appreciate them without assuming they are always superior.
35. As an English learner, I want one new-context task using a learning point from the session, so that I can try transferring it beyond the original sentence.
36. As an English learner, I want the coach to wait for and respond to my new-context attempt, so that the exercise includes observable active production.
37. As an English learner, I want support or simplification when that task remains difficult, so that the lesson does not keep adding new targets.
38. As an English learner, I want to skip or end an activity, so that I retain control over the session without being labeled as having failed or mastered it.
39. As an English learner, I want the closing feedback to distinguish independent work, hinted work, and skipped work, so that it accurately describes this session.
40. As an English learner, I want practice to work without a permanent profile or saved summary, so that I can use the first version as a single-session tool.
41. As a learner returning to the surrounding workflow, I want a brief in-conversation handoff, so that I can continue my reading or other task after practice.
42. As a learner entering from another workflow, I want checked materials and actual completed steps reused, so that the coach does not mechanically repeat work or invent progress.
43. As a skill maintainer, I want concise shared instructions and discoverable supporting material, so that ordinary use does not require loading the entire research and design history.
44. As a skill maintainer, I want structural validation separated from behavioral evaluation, so that a well-formed package is not mistaken for a good teaching workflow.
45. As a skill maintainer, I want evaluation with fresh material and observable outcomes, so that the skill is checked beyond reproducing its written examples.
46. As a skill maintainer, I want a self-contained skill and clear loading or installation guidance, so that the first version can be tried without building a plugin or connecting services.

## Implementation Decisions

### 成品與責任邊界

1. 交付單一 skill，包含精簡主指令、清楚的觸發說明，以及教學行為確實需要的參考資料。範例與較長的進階說明可按條件載入；核心等待與判斷規則不能藏在沒有明確入口的資料中。
2. 共用一套教學核心處理兩種入口；不為獨立與交接模式建立兩套糾錯邏輯。翻譯與句型支援是核心任務的一部分，不強制依賴其他已安裝的 skill。
3. 以正常可發現的 skill 為基礎，用精確的描述區分回譯練習與普通翻譯、改稿、句型問答。既有練習內的求助視為當輪調整。若提供介面中繼資料，應與能力和邊界一致。
4. 不為本版建立外部服務、資料庫、自訂介面或沒有實際需要的執行腳本。成品可獨立使用，保留日後由 plugin 封裝的可能性。

### 輸入與當輪狀態

5. 必需材料為英文原文與會影響意思的語境。交接可另外提供中文提示、真實回譯稿、已完成階段與當輪偏好；缺少會影響評估的材料時先補齊，不自行杜撰。
6. 當輪區分原文、目前採用的中文提示、原始回譯稿、後續修訂、已給提示及目前等待的回答。這些是對話中的工作資料，不是持續儲存的使用者檔案。
7. 交接只沿用有依據且檢查過的材料和進度。完成後在原對話以短收尾回到周邊任務；不把這個設計宣稱為跨 skill 的程式 API 或自動跨聊天傳輸。
8. 沒有正式程度資訊時，從短材料與實際答案提供適量支援，不先強制測驗或從單一答案推定整體能力等級。

### 教學互動與完成條件

9. 材料整理完成後，提供自行英翻中與 AI 翻譯的選擇；已有明確偏好或譯文時直接沿用適當路徑。
10. 自翻中文時，先修正影響意思的理解偏差並解釋，再以修訂版本繼續。AI 翻譯時保留必要意思與自然繁中表達，不為暗示英文答案而刻意照搬語序。提示沒有待釐清之處即可出題，不插入形式上的確認。
11. 回譯時只重貼中文提示並等待真實使用者答案，容許中文占位與未完成部分。回譯前可讀原文，期間不再重貼完整英文答案；不宣稱前文已隱藏或強制閉卷。
12. 每次評估同時參照英文原文、中文提示與使用者版本。先辨認材料失真，再判斷語言問題；原文欠佳或提示資訊不足時，先修復材料。
13. 將求助狀態、問題類型、影響程度及原文比較分開。優先處理關鍵意思偏差，同一處只教一次；沒有內容的階段直接略過。
14. 對適合自行修正的一個重點先提示一次，停下等待。若是未知用法、明確求助、中文占位或提示後仍卡住，提供示範與短解釋。提示尚未完成前不揭露完整修訂。
15. 自修互動完成後，提供最低必要改動的完整修訂。原句成立則可保留，必要改正與可選風格變化要能分辨。
16. 深入講解預設一至三點，採 B 深度：說明實際意思、目標差別、使用判準與短例子。需要時展開 C 的結構原理及相關延伸；只需提醒或使用者想簡短時採 A。講得更深時可減少考點，不把所有相關用法一次加入。
17. 原文比較在使用者留下初稿後進行，可與必要修訂自然合併。比較須說明具體語意、語域或表達效果，接受成立的替代版本，不以原文相似度評分。
18. 以一個本輪學習點出一題新情境，等待使用者產出，再給短回饋。新題不混入未教的複雜要求；仍卡住時就地提供支架或簡化，不持續累加題目。
19. 使用者可跳過、縮短或結束。收尾只描述實際完成的內容，區分獨立產出、提示後修訂及未觀察；不由當輪表現保證長期掌握、口說能力或保留效果。
20. 有具體理由時可提議增加、合併或減少活動，每次以一個實用調整為主；正常略過空階段不需重新設定，每輪不強制詢問整套偏好。

### 實作完成的交付內容

21. 提供完整可載入的 skill、必要參考資源、結構驗證結果、實際行為評估紀錄及已知限制，並說明本機載入或安裝方式。
22. 既有研究與已確認設計仍保留作為來源，成品不要求使用者或執行代理每次讀完整段討論，也不把研究成效限制轉成每輪必須展示的警告。
23. 實作版本需能在沒有長期學習檔案、其他英文 skill 或外部帳號的情況下完成核心練習。安裝到個人環境或另行封裝依後續明確任務處理。

## Testing Decisions

### 已確認的單一主要測試邊界

使用者於 2026-10-15 明確確認：以**載入完整 skill 後，使用者實際看到的對話行為**為驗收邊界。從請求與已知材料進入，觀察下一則回覆、等待行為及後續輪次；不把內部文件分段、標題、特定句子或私有思考當成測試介面。

兩種入口、翻譯選擇、提示、修訂、深度調整、再運用與收尾都經由這個邊界測試，不另拆一組與實際使用脫節的「翻譯函式」或「糾錯函式」測試。結構驗證是另行的基本檢查，不是第二個教學測試邊界。

### 好的測試與通過條件

1. 使用新英文材料、清楚語境與真實或明確標示的測試作答。測試中的學習者回覆是測試輸入，不讓受測 skill 自行編寫並假稱真人已回答。
2. 在該停下的輪次檢查是否真的等待。測試自修提示時，先只提供初稿；檢查其回覆後才送入後續修訂或求助，不能用一段完整示範稿替代跨輪觀察。
3. 判斷意思保留、必要支援、對正確替代表達的處理及下一步活動是否合適；不要求逐字命中預期措辭、固定標題或固定訊息長度。
4. 已確認的一至三點與 B／C 策略是預設節奏，需同時驗證明確的縮短或深入請求，避免測試只獎勵固定篇幅。
5. 出現核心語意誤判、錯改正確替代表達、把提示失真歸咎使用者、未等回答就假裝完成、提示中提前洩漏完整修訂，或擅自加入長期保存行為時，該案例不通過，需修正後重跑相關情境。
6. 行為評估保留輸入、實際輸出、預期行為判準與差異。語境依賴的判斷須說明理由；不以籠統的「看起來不錯」或格式檢查通過結案。
7. 發現問題後修正共用規則或相關指引，重跑失敗案例與受影響路徑；避免只為某一句測試材料硬編特殊答案。

### 覆蓋的可觀察行為

| 情境 | 驗收觀察 | 對應 user stories |
| --- | --- | --- |
| 明確請求回譯，及只有一般英文／翻譯請求 | 前者啟動練習，後者維持原任務 | 1–2 |
| 缺原文、長文與影響意思的歧義 | 補齊必要資訊或合理選段，不捏造 | 4–6 |
| 自翻中文時誤解關鍵意思 | 修正理解並用修訂提示繼續 | 7–10 |
| 明確要求 AI 翻譯或已有可用譯文 | 尊重既定選擇，不重複設定 | 8、10 |
| 中文提示已備妥，尚未有回譯稿 | 出題後停下，不自行補學習者答案 | 11–12 |
| 中文占位、留空、明確求助 | 提供合適支援，不虛構英文錯誤 | 13–14 |
| 可自行修復的一個重點 | 提示後等待，不先貼完整修訂 | 15、17 |
| 提示後仍卡住或要求直接答案 | 轉為示範，不連續猜題 | 14、16 |
| 文法成立但意思反向 | 指出實際誤讀，優先修復核心意思 | 18–20 |
| 同一處符合多種類型 | 解釋一次，修訂保留原意 | 21–22 |
| 正確替代表達與無錯誤答案 | 接受或保留，不為填分類挑錯 | 23–24、31 |
| 中文提示漏資訊或原文有錯 | 先修材料，分清補充學習與學習者錯誤 | 25–26 |
| 普通回饋、追問原因與要求簡短 | 分別展現 B、按需 C 與縮短 A | 27–30 |
| 調整活動或比較原文亮點 | 建議具體且有用，不反覆全套設定，不宣稱原文必然較好 | 32–34 |
| 新情境作答成功、卡住、跳過 | 等待再回饋，適量支援，如實收尾 | 35–39 |
| 沒有歷史檔案的新練習 | 可正常完成，不要求保存紀錄或摘要 | 40 |
| 其他流程交接部分材料與進度 | 檢查後銜接，完成後在原對話返回，不捏造進度 | 3、41–42 |
| 參考資料按需使用與獨立載入 | 能達成相應分支，不依賴討論歷史、其他 skill 或外部服務 | 43、46 |

### 新材料示例與評估控制

下列是適合另製測試輸入的方向，不是要求在 skill 內加入的固定示範答案：

- 原文價格「fell by ten percent」，回譯稿寫成「fell to ten percent」：辨認減少幅度與最後數值的差別。
- 原文「The train was delayed because of heavy rain」，回譯稿「Heavy rain delayed the train」：接受在此語境保留意思的不同句法。
- 原文「She moved to Tokyo in April」，中文提示漏掉月份：不能把學習者沒有寫四月判成漏譯。

使用已知設計案例可做回歸檢查，但驗收不能只重播那些例句。若由另一執行代理做前向試跑，僅提供 skill、原始任務與所需材料；預期判準留在評估側，避免受測回覆照抄答案。這是可採用的評估方式，不要求必須啟用平行代理。

### 基本結構檢查與現有先例

檢查 skill 名稱、必要中繼資料、未完成佔位內容、參考資料連結與可載入性。若後續實作確實需要腳本，另驗證其有意義的外部行為，不為比對指令文字而建立測試。

目前專案僅有研究、設計與決策文件，沒有既有可執行測試套件、skill 成品或程式測試接點。既有「設計覆蓋走查」與對話原型是案例設計先例，不是已通過的行為測試。沿用其情境分類並補新材料即可，不引入沒有需求的測試框架。

## Out of Scope

- 重新研究或重開已確認的教學方向，除非實作或驗收揭露具體矛盾。
- Plugin 封裝、公開上架、MCP server、自訂 UI、外部帳號與題庫服務。
- 長期學習紀錄、自動錯題庫、跨聊天能力追蹤、複習排程與永久偏好儲存。
- 語音輸入整合、發音評估及宣稱文字練習已證明口說成效。
- 用原文相似度、固定措辭或特定標題作主要教學分數。
- 以本版一次產出或設計檢視宣稱已驗證長期學習成效。

## Further Notes

### 已確認決策與來源

- [完整教學設計 v1.0](../../docs/design/back-translation-spec.md)：已經使用者確認，作為本實作規格的教學依據。
- [詞彙表](../../GLOSSARY.md)：教學回譯、中文提示、回譯稿、合理替代表達、遷移運用與教學階段的共用定義。
- [已結案的 wayfinder 地圖](../back-translation/map.md)：研究與設計決策的索引；其決策票不是實作票。
- [設計覆蓋走查](../../docs/design/design-review.md)、[對話原型](../../docs/design/teaching-loop-prototype.md)、[深度比較](../../docs/design/feedback-depth-comparison.md)：設計階段的案例資產。
- [方法研究](../../docs/research/back-translation-method.md)、[回饋與遷移研究](../../docs/research/feedback-and-transfer.md)：一手來源、相鄰證據與不能推論的範圍。
- [Skill 與 plugin 能力查核](../../docs/research/skill-plugin-boundary.md)：封裝選擇的依據。

### 發布與接續

本規格最初發布於既有本機 Markdown 追蹤器，狀態為 `ready-for-agent`。測試邊界已由使用者明確接受。2026-10-15，四張實作票完成並合併至 `integration/back-translation-skill`，整合審查完成後關閉本規格。

實作拆分見 [票務索引](ticket-breakdown.md)，驗收與兩軸審查見 [整合紀錄](../../evaluations/integration-review.md)。本規格保留為交付與後續維護的需求基準；先前 wayfinder 決策票與本次實作票仍為不同紀錄。

## Comments

- 2026-10-15：使用者確認以「載入完整 skill 後，使用者實際看到的對話」為測試邊界；使用新材料檢查等待、提示、正確替代表達及中文提示失真，格式另檢查。
- 2026-10-15：依 to-spec 將既有設計、決策與驗收要求整合為本規格，發布為 ready-for-agent。本次未開始實作、建立實作票或執行 skill 行為測試。
- 2026-10-15：依 implement-spec 完成四張實作票，交付可載入的單次回譯 skill、實際跨輪評估與載入說明。以 `main` 為基準的整合審查在 `9cc6056` 完成，Standards／Spec 各 0 待修項。結構、差異與連結檢查通過；安裝、發現介面與人類學習成效未宣稱已驗證。父規格結案。
