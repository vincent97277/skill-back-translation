# 回譯英文練習

首版成品是 [back-translation-practice](skills/back-translation-practice/SKILL.md)：以英文原文、繁體中文提示與學習者實際英文回譯，練習主動表達，再做一次新情境運用。支援自行英翻中或 AI 提供中文、材料修復、提示自修、詳略調整，以及在同一閱讀對話中依已有進度續接。預設一至三句、約十分鐘；可隨時求助、跳過或結束。

## 直接試用

在能讀取本專案檔案的 Codex 對話中，請求：

> 讀取本專案的 `skills/back-translation-practice/SKILL.md`，用完整 skill 帶我做回譯練習。英文原文：［貼上英文及會影響意思的語境］。

這是本次實際評估採用的載入方式。可一併指定「我自己翻中文」或「請你提供中文」，也可以只提供原文後選擇。若從閱讀流程接入，可在**同一對話**提供已採用中文、實際回譯稿、已給提示、正在等待的回答與想接回的閱讀問題；只提供實際已有的進度即可，不需要填表或保存摘要。

## 選擇性本機安裝

專案的 `skills/` 是交付資料夾，本次沒有把它安裝到個人環境。要讓 Codex 正常發現它，可在另一次明確的安裝操作中，把完整 `skills/back-translation-practice/` 資料夾複製至目前官方文件列出的使用者位置 `~/.agents/skills/back-translation-practice/`，或本專案的 `.agents/skills/back-translation-practice/`。先確認同名目標不存在，保留既有版本與設定；不要同時放兩份同名 skill。依 [OpenAI 官方本機 skill 文件](https://learn.chatgpt.com/docs/build-skills)，Codex 會偵測新增／修改；若未出現可重新啟動，再以 `$back-translation-practice` 請求練習。不同版本的主機設定可能有差異；本次未驗證安裝、自動發現或選擇器呈現。

## 成品與驗證

執行時只需要 `skills/back-translation-practice/`，目前只有一份 `SKILL.md`，沒有外部參考或執行依賴。不需要其他英文 skill、外部帳號、長期學習檔案、錯題庫或排程。`evaluations/`、`docs/`、`.scratch/` 與 `GLOSSARY.md` 是維護、來源與驗收資料，無須隨 skill 載入。

結構檢查和教學行為分開驗證：結構由 skill-creator 的 `quick_validate.py` 檢查；行為以載入完整 skill 後的實際跨輪回覆為邊界，學習者測試答案逐輪提供，判斷語意、公平性、等待及續接，不比對固定標題、指令文字或原文相似率。

- [整合驗收與限制](evaluations/ticket-04/evidence.md)：不同交接進度、完成後返回、整體覆蓋索引與最終檢查。
- [整合分支雙軸審查](evaluations/integration-review.md)：Standards 與 Spec 均無待修項，四張實作票已完成；審查基準與限制分別記錄。
- [核心練習](evaluations/ticket-01/evidence.md)、[自翻與材料修復](evaluations/ticket-02/evidence.md)、[提示與深度調整](evaluations/ticket-03/evidence.md)：前置票的實際對話、觀察到的失敗及後續修正。

這些是有限的模型對話與明確標示的測試作答，沒有以人類學習者試驗；不能據此保證長期記憶、口說能力、熟練度或學習成效。對話交接是在原對話中續接，不是跨 skill 程式 API 或跨聊天自動傳輸。

## 設計來源

- [完整設計稿](docs/design/back-translation-spec.md)、[實作規格](.scratch/back-translation-skill/spec.md)、[設計檢視](docs/design/design-review.md)。
- [決策地圖](.scratch/back-translation/map.md)、[詞彙表](GLOSSARY.md)。
- [回譯法研究](docs/research/back-translation-method.md)、[回饋與遷移研究](docs/research/feedback-and-transfer.md)。
- [對話原型](docs/design/teaching-loop-prototype.md)、[深度比較](docs/design/feedback-depth-comparison.md)是設計階段的假想案例；實際驗收對話另存於 `evaluations/`。
