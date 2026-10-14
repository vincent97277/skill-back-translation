# Skill 與 plugin 的封裝邊界

查核日期：2026-10-15（Asia/Taipei）。本文件記錄產品能力事實與設計推論，尚未決定封裝方案。

## 官方文件確認的事實

- Skill 以 `SKILL.md` 和選用的參考資料、範例及其他資源描述可重複的工作流程。它可以在沒有 MCP server 的情況下運作。[OpenAI：Skills](https://developers.openai.com/plugins/concepts/skills)
- Plugin 是可安裝的封裝，可以包含一個或多個 skill，也可以整合 MCP server。當既有能力足以完成工作時，官方建議從最小的合適組成開始。[OpenAI：Plugin architecture](https://developers.openai.com/plugins/concepts/plugins)
- MCP server 負責即時資料、驗證、授權與受控操作；skill 負責工作流程與資源。[OpenAI：Skills](https://developers.openai.com/plugins/concepts/skills)

## 對本案的初步推論，待討論

回譯教學首先是對話工作流程。若需求只有接收文章、逐步練習、提示與回饋，skill 是可考慮的核心單位；未來可由 plugin 封裝。兩者並非互斥選項。

若後續要求跨聊天保存學習紀錄、排程複習、讀寫外部題庫或提供自訂練習介面，需另行查核儲存、工具與平台整合方式；skill 本身的存在不能作為這些能力已具備的證據。

本案的設計仍須決定：完整練習與可由其他流程使用的局部練習，是否共用同一組教學規則、如何傳入上下文，以及完成後回傳什麼學習結果。
