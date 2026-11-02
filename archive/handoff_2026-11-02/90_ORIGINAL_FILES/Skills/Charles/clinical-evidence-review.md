---
name: clinical-evidence-review
description: 證據到決策審查醫療問題。Use when answering clinical, diagnostic, therapeutic, prognostic, medication, guideline, or patient-specific health questions that require current evidence, risk–benefit appraisal, applicability, dosing safety, or separation of exam answers from real-world practice.
---

# Clinical Evidence Review

用**證據到決策**流程處理醫療問題：先辨認問題模式與臨床決策，再取得能回答該問題的當前證據，評估效果、傷害、確定性與病人適用性，最後輸出與證據強度一致的結論。

本 skill 是醫療問題的高門檻外層流程。外部資料檢索與來源鏈使用 `source-backed-analysis`；共用事實、宣稱、推論與未知分類使用 `/Skills/Charles/evidence-taxonomy.md`。若使用者質疑既有醫療回答，以 `independent-reassessment` 為外層，本 skill 負責臨床證據與適用性審計。

## 0. 安全與時效分流

先判斷是否存在需要立即行動、不能等待完整文獻審查的情況：

- 可能危及生命、肢體、視力、神經功能或孕產安全的症狀。
- 可能的嚴重藥物不良反應、過量、戒斷、過敏或交互作用。
- 病情快速惡化、生命徵象不穩定、意識改變或無法安全自我照護。
- 回答若被直接執行，可能造成延誤治療、停用必要藥物或高風險處置。

遇到急迫風險時，先給明確的就醫或升級處置，再補充證據背景。藥物、指引、適應症、警示、劑量與法規可能變動時，先確認當前版本。

**完成條件：**已決定可進入一般證據審查，或已先完成必要的急迫處置建議與風險界線。

## 1. 判定問題模式

將任務指定為一個主要模式：

1. **考試模式** — 目標是標準答案、鑑別線索與選項判讀。
2. **一般知識模式** — 解釋疾病、機轉、檢查或治療原理，不針對單一病人做決策。
3. **臨床決策模式** — 比較診斷、治療、預防、預後或追蹤策略。
4. **病人特定模式** — 結論取決於個人病史、檢驗、共病、藥物、腎肝功能、妊娠或偏好。
5. **文件審查模式** — 解讀 guideline、論文、藥品仿單、病例摘要或院內規範。

同一問題若跨模式，先回答主要模式，再標示其他模式會如何改變結論。考試答案與臨床實務可能不同時，必須分開呈現。

**完成條件：**主要模式、使用者所需技術深度與答案用途均已明確。

## 2. 建立臨床問題框架

把問題改寫成能被證據回答的命題。依類型記錄：

- **治療／預防：**Population、Intervention、Comparator、patient-important Outcomes、time horizon。
- **診斷：**target condition、index test、reference standard、clinical setting、decision threshold。
- **預後／風險：**population、predictor/model、outcome、time horizon、intended use。
- **傷害／病因：**exposure、comparator、outcome、latency、重要混雜。
- **藥物：**indication、dose/route、renal/hepatic function、interactions、contraindications、monitoring。

先指定真正影響決策的 outcome，區分：

- 死亡、功能、症狀、生活品質、住院與嚴重不良事件等病人重要結局。
- surrogate、影像、實驗室或複合終點。
- 短期與長期結局。

**完成條件：**population、比較方案、重要 outcome、時間範圍與決策門檻足以指導檢索與判讀。

## 3. 取得當前且適配的證據

執行 `source-backed-analysis` 的 discovery 與 verification passes。依問題類型優先尋找：

- 當前且適用司法管轄或專科的 clinical practice guideline、consensus 或官方建議。
- 系統性回顧、meta-analysis、evidence report 與 pivotal trials。
- 對診斷準確度、預後模型、真實世界安全性或罕見傷害最合適的原始研究。
- 藥品仿單、監管警示、正式藥物資料庫與機構用藥規範。
- 台灣衛福部、健保、專科醫學會、院內 formulary 或可近性資料，當地執行性會改變答案時。

指引是決策來源，不是自動最高證據。確認其發布／更新日期、證據搜尋截止日、族群、利益衝突、推薦強度與底層研究。只讀摘要不足以支持高風險結論時，取得全文或可檢視的方法與結果。

**完成條件：**每個關鍵臨床主張都有當前且問題適配的來源，或已明確保留無法取得的證據缺口。

## 4. 建立 clinical evidence ledger

讀取 `/Skills/Charles/evidence-taxonomy.md`，並為每項會改變決策的主張增加下列欄位：

| 欄位 | 內容 |
|---|---|
| Clinical question | 精確的 PICO／診斷／預後／傷害命題 |
| Evidence type | guideline、systematic review、RCT、observational、diagnostic study、label 等 |
| Population and setting | 納入族群、疾病嚴重度、照護層級與排除條件 |
| Intervention / comparator | 實際治療、劑量、技術與對照 |
| Outcome and horizon | outcome 定義、追蹤期間與是否為 surrogate |
| Effect | 相對效果與絕對效果；必要時 NNT／NNH 或測試後機率 |
| Harms and burden | 不良事件、監測、侵入性、成本與治療負擔 |
| Certainty | 高／中／低／極低或無法判定，附主要降級原因 |
| Applicability | 與目標病人的直接性、基準風險及當地可執行性 |
| Status | 支持／部分支持／反駁／未決 |

沒有適當分母、基準風險或時間範圍時，不自行產生絕對風險與 NNT／NNH。臨床證據確定性是對 outcome 證據體的判定，不等同 `/Skills/Charles/evidence-taxonomy.md` 的一般來源信心。

**完成條件：**每項關鍵主張均可追溯到族群、介入、結局、效果、傷害、確定性與適用性。

## 5. 評讀證據確定性

依問題類型讀取 `/Skills/Charles/clinical-evidence-reference.md` 的對應分支。至少檢查：

- 研究設計是否能回答提出的問題。
- risk of bias、混雜、選擇偏差、測量偏差與缺失資料。
- 結果是否一致、精確且直接適用。
- publication bias、選擇性報告、多重比較與提前終止。
- outcome 是否為病人重要結局，或只是未驗證 surrogate。
- 統計顯著是否對應臨床重要效果。
- 相對效果在目標病人的基準風險下會產生多大的絕對效益與傷害。

研究未證明差異，不等同證明等效；非劣性、等效性與優效性必須依其設計門檻解讀。

**完成條件：**主要效益與傷害均有確定性判定，且所有足以改變判斷的限制已具體說明。

## 6. 執行問題分支

### Therapeutic / preventive branch

比較病人重要效益、嚴重與常見傷害、治療負擔、可逆性、監測需求與替代方案。把相對風險轉成與目標族群基準風險相符的絕對效果；資料不足時只呈現可支持的尺度。

### Diagnostic branch

分開評估 sensitivity、specificity、likelihood ratios、pretest probability、post-test probability、reference standard、spectrum bias 與 verification bias。檢查 test 結果是否會改變管理；高準確度但不改變決策的檢查不自動具有臨床價值。

### Prognostic / prediction branch

區分 association、prognosis 與可用於決策的 prediction。檢查 discrimination、calibration、validation population、time horizon、missing data、clinical utility 與模型是否已外部驗證。單一顯著 predictor 不等同可靠預測工具。

### Medication / dosing branch

使用當前權威藥物來源核對 indication、劑量、route、頻率、療程、最大劑量、腎肝調整、妊娠哺乳、年齡體重、交互作用、過敏、contraindications、monitoring 與停藥／taper 條件。缺少會影響安全劑量的病人資料時，標示條件式範圍，不填造具體劑量。

### Guideline-conflict branch

指引不一致時，比較：問題範圍、證據截止日、推薦方法、底層研究、基準風險、資源與價值假設、利益衝突及司法管轄。呈現真正的分歧，不以機構名氣投票。

### Exam branch

先直接給標準答案與關鍵判別點；逐選項說明其成立條件與錯誤原因。若考試慣用簡化規則與臨床實務不同，另加「臨床補充」，不讓補充改寫題目要求的答案。

**完成條件：**相關分支的專屬偏差、指標與安全項目均已檢查。

## 7. 評估病人與場域適用性

病人特定模式下，明確列出會改變決策的 modifier：

- 年齡、性別、生理狀態、體重、妊娠與哺乳。
- 疾病嚴重度、病程、既往治療反應與基準風險。
- 腎功能、肝功能、血液學、心電圖或其他必要安全數據。
- 共病、frailty、認知、功能狀態與預期壽命。
- 目前藥物、交互作用、過敏與 adherence。
- 病人價值、治療目標、可接受負擔與風險偏好。
- 台灣可取得性、健保給付、院內限制、追蹤與監測能力。

資料缺少時，把結論寫成條件式：「在 X 成立時，Y 較合理」；不得默認未提供的病史、檢驗或偏好。研究 population 與目標病人差異愈大，推薦語氣應愈保守。

**完成條件：**所有已知 applicability modifiers 已納入，未知但可能逆轉決策者保持可見。

## 8. 形成證據到決策結論

依證據確定性、效益與傷害平衡、病人價值、可執行性與替代方案，使用一個主要結論：

- **支持** — 目前證據與適用性支持該策略。
- **有條件支持** — 對特定族群、偏好或條件合理，但不是普遍最佳。
- **證據不足** — 尚不能可靠選擇；指出最能解除不確定性的資料。
- **不支持常規使用** — 現有證據未顯示足夠淨效益，或適用性不足。
- **應避免／禁忌** — 已有明確傷害、contraindication 或不利效益傷害平衡。

建議強度不能高於證據與適用性允許的程度。低確定性證據仍可形成強烈安全建議，但必須說明原因，例如巨大傷害、不可逆風險或可用的低風險替代方案。

**完成條件：**結論直接回答決策，且推薦方向、強度、條件與確定性可逐項對回 ledger。

## Response contract

### 臨床決策／病人特定模式

```markdown
**結論：** [支持／有條件支持／證據不足／不支持常規使用／應避免。]
**證據確定性：** [高／中／低／極低／無法判定。]
**對此情境的適用性：** [高／中／低。]

## 關鍵證據
[效益、絕對效果、傷害與限制；引用緊鄰主張。]

## 臨床判讀
[證據如何轉化成此病人或場域的決策。]

## 執行與監測
[必要檢查、劑量條件、追蹤、停止條件或需補資料。]
```

### 一般知識模式

先直接回答，再用最少篇幅區分共識、證據限制與仍具爭議之處。

### 考試模式

```markdown
**答案：X。**

**關鍵判別：** [一句核心理由。]

**各選項：** [逐項說明。]

**臨床補充：** [僅在與考試簡化不同時加入。]
```

## Failure modes

- **Guideline worship** — 把指引推薦當成脫離日期、族群與底層證據的永恆事實。回到更新日與證據基礎。
- **Abstract-only certainty** — 只讀摘要便對高風險問題給強結論。取得方法、結果與限制。
- **Relative-risk inflation** — 只報相對效果，使低基準風險看似巨大。補上可支持的絕對效果。
- **Surrogate substitution** — 把生物標記改善當成死亡、功能或生活品質改善。分開呈現。
- **P-value medicine** — 用 p 值二分有效／無效。評估效果量、區間與臨床重要性。
- **Population laundering** — 把研究族群結果直接套到未納入的年齡、嚴重度、共病或孕產族群。降低適用性或保留未知。
- **Recommendation laundering** — 研究作者意見、當事方主張或弱共識被寫成標準治療。標示來源角色與推薦強度。
- **Indication creep** — 把特定適應症、線別或時間窗擴張到所有病人。收窄至已研究範圍。
- **Dose hallucination** — 缺少病人資料或當前藥物來源仍輸出精確劑量。先核對並保留條件。
- **Contraindication omission** — 給治療建議卻未檢查關鍵禁忌、交互作用與腎肝調整。執行 medication branch。
- **Exam–practice collapse** — 用臨床爭議模糊標準考題，或把考試口訣當真實病人決策。分開模式。
- **Local-context omission** — 忽略台灣核准、給付、可取得性與監測條件。降低可執行性判定。
- **Stale safety** — 使用過時劑量、警示或指引。確認當前版本與更新日期。

## Final completion criterion

所有相關階段的完成條件、專屬分支與 Response contract 均成立後，才完成臨床證據審查。
