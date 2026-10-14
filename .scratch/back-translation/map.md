# 回譯英文練習：從研究走向可重用的教學設計

Labels: wayfinder:map
Status: resolved

## Destination

與使用者共同完成有研究依據、可供後續實作的完整設計，涵蓋方法定義、學習目標、互動流程、回饋規則、對話範例與 skill／plugin 封裝建議。
當必要決策均經討論、範例經使用者檢視，且設計足以交付實作，才算抵達終點。

## Notes

- 使用者於 2026-10-15 確認：本次先完成完整設計，實作與安裝留待之後。
- 依 wayfinder、grilling、domain-modeling 推進；研究依 research skill 使用背景研究代理。
- 本機 Markdown 為目前追蹤器。使用 `.scratch/<effort>/issues/NN-<slug>.md`，依 issue-tracker-local.md 記錄類型、狀態、認領與阻擋關係。
- 尚未提供正式追蹤器，若日後需要可執行 `/setup-matt-pocock-skills`。目前目錄沒有 Git 儲存庫或 remote；研究保留於本機檔案，無可建立及推送的遠端研究分支。
- 已知起點：接收英文原文；英中翻譯可由使用者練習或由 AI 提供；使用者依繁體中文回譯英文；AI 教學應促成理解、好奇與舉一反三。
- 2026-10-15：使用者完成整體檢視並確認設計；本次目的地已達成，所有子票均已解決。
- 每個 session 至多解決一個非研究票；繪圖階段不代替使用者完成教學決策。
- Skill 的能力邊界參考官方文件研究：[Skill 與 plugin](../../docs/research/skill-plugin-boundary.md)。
- 完整交付稿見 [單次回譯英文練習設計](../../docs/design/back-translation-spec.md)，設計版本 1.0，可供後續實作。

## Decisions so far

- [回譯法的定義、直接證據與適用限制](issues/01-method-evidence.md)：教學回譯著重察覺表達缺口，容許適切替代表達；直接成效證據有限，不能視為本案效果保證。
- [哪些回饋與再練習機制有證據支持](issues/02-feedback-evidence.md)：區分當下修訂與日後運用；提示、示範與再提取有鄰近依據，具體 AI 教學規則仍須試用。
- [首要學習目標與最小可用練習範圍](issues/03-learning-goals.md)：以主動表達及遷移運用為主，先以一至三句、文字互動、約十分鐘試走。
- [從中文提示到英文回饋的完整教學循環](issues/04-teaching-loop.md)：採理解對比的 B 深度，需要時展開 C；支援、自修、原文比較與新情境運用依答案彈性安排。
- [獨立 skill 與其他英文流程共用時的邊界](issues/05-reuse-boundary.md)：單一 skill 支援兩種入口，未來可由 plugin 封裝；本版只做單次練習。
- [設計何時足以交付實作](issues/06-design-validation.md)：案例與規格覆蓋走查完成，使用者確認完整設計，已可交付實作。

## Not yet specified

無。本次設計所需決策與整體檢視均已完成。

## Out of scope

- 本次不實作、安裝或公開發布 skill／plugin。
- 不建立外部服務、帳號串接或持續儲存系統；若設計需要，只記錄能力需求與後續實作邊界。
- 長期學習紀錄、自動錯題庫、跨聊天能力追蹤與複習排程不納入本版，依使用者 Q9 的選擇留待之後。
