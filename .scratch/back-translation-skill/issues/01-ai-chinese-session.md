# 01: AI 提供中文的完整單次回譯練習

**What to build:** 使用者提供英文並明確選擇由 AI 翻成繁中後，能用一個實際可載入的 skill 完成中文提示、英文回譯、B 深度回饋、原文比較、新情境產出與收尾。這是可獨立試用的第一條完整路徑；本票不假稱尚未完成的自翻、提示自修或交接擴充已可用。

**Blocked by:** None (can start immediately).

**Status:** closed

## Acceptance criteria

- [x] 成品可獨立載入，主指令與必要參考資料可被找到；不依賴討論歷史、其他英文 skill、外部服務或學習檔案。
- [x] 明確回譯請求能開始練習；單純翻譯、改稿或一般英文輸入不被自動改成回譯課程。使用者明確選擇 AI 翻譯時不重問偏好。
- [x] 對一至三句、語境充足的英文提供自然且保留必要意思的繁中提示；出題時不重貼完整英文答案，不宣稱先前原文已隱藏。
- [x] 出題後實際停下等待使用者回譯；接受未完成片段、中文占位與明確求助，提供對應支援，不自行生成並假稱使用者已答。
- [x] 回饋同時參照原文、中文提示與使用者原稿；文法成立但核心意思錯置時指出具體誤讀，問題類型與影響程度分開，同一問題只講一次。
- [x] 使用最低必要改動提供完整修訂，正確替代表達予以接受；無錯誤時可保留原句，並清楚區分必要修正與可選的原文表達。
- [x] 預設用 B 深度深入教一至三點，包含意思差別、使用判準與短例子；不強制湊滿分類或宣稱原文一定比較好。
- [x] 選一個當輪學習點出新情境題，等待作答再回饋；卡住時適量支援。使用者可跳過或結束，收尾僅描述實際產出與支援，不宣稱長期掌握。
- [x] 完成必要結構檢查，並用未直接複製教學範例的新材料，實際跨輪驗證 AI 中文路徑、中文占位、意思偏移、正確替代表達與新情境產出；保存輸入、實際回覆、判準及結果，不以固定措辭比對代替行為評估。
- [x] 成品與評估紀錄留在專案，提供載入或安裝方式；不自行安裝、發布、保存長期紀錄或要求使用者保留摘要。

## Source coverage

來源：回譯英文練習 skill：實作規格 v1.0。

主要 user stories：1、2、8、10–14、18–24、27、28、31、34–40、43–46。故事 8、10、27、31、37–39、43–46 在後續票也有不同路徑的延伸驗收。

## Comments

- 2026-10-15：to-tickets 拆分草案，尚待使用者確認，不是已發布的 ready-for-agent 實作票。

- 2026-10-15：使用者呼叫 implement-spec，授權依四張拆分執行；草案轉為正式實作票。

## Resolution

- 2026-10-15: Implemented the self-contained core skill with the AI-provided Chinese session, B contrast feedback, valid alternatives, direct help, one new-context activity and truthful close. Runtime package: `skills/back-translation-practice`.
- Evidence: [ticket 01 evaluation](../../../evaluations/ticket-01/evidence.md). Missing-entrypoint red was observed before creation. Actual fresh-actor conversations are preserved; one closing-attribution failure was corrected and the affected full path rerun. Structural validation passed independently. The evaluation notes explicitly record fixture and installation limitations.
- Later tickets own self-translation/material repair, hint-first/adaptive depth, and surrounding-workflow handoff. No installation, plugin publication, or persistent profile was added.
