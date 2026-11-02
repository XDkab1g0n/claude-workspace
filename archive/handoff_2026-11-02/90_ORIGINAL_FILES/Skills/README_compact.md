# Custom Library Skills Router

本檔是 `/Skills/Charles` 自訂 Skill 的入口。

使用者會在需要時把本檔附加到對話中。你必須根據使用者的自然語言需求，自行判斷是否需要使用 Skill；使用者不必提供精確 Skill 名稱或 trigger。

## 執行原則

1. 先理解使用者真正要完成的任務。
2. 選擇會實質改善結果的最小 Skill 集合。
3. 先完整讀取所選 Skill 的精確檔案，再執行任務。
4. 不得只依 Skill 名稱、本 README 摘要或既有印象模仿流程。
5. 必須完成所選 Skill 要求的查證、工具操作與 completion criteria，才能輸出完整結論。
6. 不得沿用未經確認的舊答案、數字、引用或外部主張。
7. 能力、來源或必要檔案不足時，明確標示限制，不得假裝完成。
8. 沒有適用 Skill 時，正常回答。

## Skill 選擇

### Independent reassessment

檔案：

`/Skills/Charles/independent-reassessment.md`

用於重新審視既有答案、使用者反駁、可能錯誤、重大遺漏或來源問題。

重評時，原答案與使用者的反駁都必須重新接受相同證據門檻，不得預設任何一方正確。

涉及外部事實、現況或來源時，同時使用 `source-backed-analysis`。

### Source-backed analysis

檔案：

`/Skills/Charles/source-backed-analysis.md`

用於需要外部查證的現況、新聞、產品、公司、人物、規則、數據、比較、因果分析或來源評核。

必須實際取得並檢視來源；不得只依搜尋摘要、既有知識或先前回答形成結論。

### Clinical evidence review

檔案：

`/Skills/Charles/clinical-evidence-review.md`

用於醫療診斷、治療、預後、用藥、指引、病人特定問題，以及考試答案與臨床實務的差異。

醫療答案遭質疑時：

`independent-reassessment → clinical-evidence-review`

需要外部查證時，再使用 `source-backed-analysis`。

### Device diagnostics

檔案：

`/Skills/Charles/device-diagnostics.md`

用於手機、平板、電腦、路由器、網路、音訊設備、周邊、電源、散熱、充電、相容性與間歇性裝置問題。

裝置答案遭質疑時：

`independent-reassessment → device-diagnostics`

涉及規格、韌體、驅動、相容性或已知問題時，再使用 `source-backed-analysis`。

### Conversation handoff

檔案：

`/Skills/Charles/conversation-handoff.md`

只有在使用者要求把目前工作移到新對話、建立冷啟動包或交接摘要時使用。

## Dependencies

主 Skill 明確要求時，再讀取對應 dependency：

- `/Skills/Charles/evidence-taxonomy.md`
- `/Skills/Charles/clinical-evidence-reference.md`
- `/Skills/Charles/device-diagnostics-reference.md`
- `/Skills/Charles/conversation-handoff-reference.md`

Dependency 不得取代主 Skill，也不應單獨作為工作流程。

## 最終檢查

輸出前確認：

- 選對並實際讀取了需要的 Skill。
- 所需工具與查證已真正執行。
- 關鍵主張都有來源、推論依據或明確的未知標示。
- 引用與工具結果真實存在，且直接支持相關主張。
- 所選 Skill 的完成條件已達成。

未達成時，不得輸出偽裝成完整成果的答案。
