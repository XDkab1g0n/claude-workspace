# Clinical Evidence Review — Branch Reference

本檔只在 `clinical-evidence-review` 已判定問題模式並建立臨床問題框架後使用。它提供各問題類型的評讀標準，不取代對實際研究、指引與病人資料的檢視。

## 證據來源與問題適配

來源強度取決於問題，而不是固定排行榜：

- **治療／預防：**適當執行的 RCT、系統性回顧與可解釋異質性的 meta-analysis 通常最能估計介入效果；罕見或長期傷害常需大型觀察性資料。
- **診斷：**以目標臨床場域連續或適當抽樣、index test 與 reference standard 盲性比較的診斷準確度研究。
- **預後：**前瞻性 cohort、適當 follow-up、清楚 outcome、充分事件數、校準與外部驗證。
- **傷害／病因：**依暴露可隨機化與否，使用 RCT、cohort、case-control、registry、pharmacovigilance 或自然實驗；重點是混雜與偵測能力。
- **罕見疾病／特殊族群：**可能依賴單臂研究、病例系列、間接證據或機轉資料；結論需反映限制。
- **Guideline：**用於整合證據、價值、資源與執行條件；其強度受搜尋截止日、方法與底層證據限制。

## 證據確定性 domains

依每個 outcome 分別評估，不給整篇研究單一模糊分數：

1. **Risk of bias** — randomization、allocation concealment、blinding、deviations、missing data、outcome measurement、selective reporting。
2. **Inconsistency** — 研究方向與效果差異是否可由 population、dose、setting 或方法解釋。
3. **Indirectness** — population、intervention、comparator、outcome、time horizon 或場域是否偏離決策問題。
4. **Imprecision** — 信賴區間是否跨越會改變決策的效益與傷害門檻；事件數是否不足。
5. **Publication bias** — 小型正向研究、未發表資料、產業贊助與 outcome reporting 是否可能扭曲結果。

觀察性研究若具大型效果、dose-response、或所有合理混雜只會削弱觀察效果，可提高信心；若存在重大 residual confounding，維持保守。

## 效果量與臨床重要性

- **Dichotomous outcomes：**RR、OR、HR 與 risk difference 不可互換。優先把相對效果套用到相關基準風險，呈現每 100 或 1,000 人的絕對差異。
- **Continuous outcomes：**確認量表方向、範圍、minimal important difference 與 baseline change；standardized mean difference 需轉回可理解尺度。
- **Time-to-event：**HR 不等同固定時間點的 risk ratio；檢查 proportional hazards 假設與指定時間點絕對風險。
- **Composite outcomes：**拆解各 component 的重要性、頻率與治療效果，避免由次要事件驅動整體顯著。
- **NNT／NNH：**必須附 outcome、期間、基準風險與計算方法；不同風險族群不能直接沿用同一數字。
- **Noninferiority：**確認 margin 的臨床合理性、assay sensitivity、per-protocol 與 intention-to-treat 結果，以及是否只是「未達顯著差異」。

## 診斷研究評讀

- 明確 target condition、clinical setting 與使用目的：rule-in、rule-out、screening、triage 或 confirmatory。
- Index test 門檻是否事先指定；是否在不知 reference standard 結果下判讀。
- Reference standard 是否足夠可靠；所有或隨機抽取的病人是否接受相同 reference standard。
- 是否使用 case-control 極端病例造成 spectrum bias。
- 報告 sensitivity、specificity、LR+、LR− 與不確定性；結合 pretest probability 估計 post-test probability。
- 檢查 downstream consequences：false positive、false negative、追加檢查、治療與病人重要 outcome。

## 預後與風險模型評讀

- 區分 etiologic association 與 prediction；預測模型不要求每個 predictor 都是因果。
- 檢查 sample size、events per parameter、missing data、overfitting、internal validation 與 external validation。
- **Discrimination：**能否排序風險，不代表機率準確。
- **Calibration：**預測機率與實際風險是否相符，且需在目標場域重新確認。
- **Clinical utility：**使用模型是否比既有策略改善決策或 net benefit。
- 模型跨族群、時間、醫院或治療時代使用時，評估 recalibration 或 performance drift。

## 藥物與劑量安全檢查

在輸出具體用藥方案前核對：

1. 適應症、治療線別與病原／疾病條件。
2. 年齡、體重、body surface area 或其他 dosing basis。
3. 腎功能指標與使用公式；透析、CRRT、AKI 或快速變化狀態。
4. 肝功能、Child-Pugh 或特定藥物限制。
5. route、loading dose、maintenance dose、間隔、療程與最大劑量。
6. allergy、cross-reactivity、pregnancy、lactation 與生殖風險。
7. pharmacokinetic／pharmacodynamic interactions、QT、serotonergic、bleeding、CNS depression 等重要交互作用。
8. 必要 baseline tests、therapeutic drug monitoring、療效與毒性追蹤。
9. hold、taper、discontinuation、failure 與 escalation criteria。
10. 台灣核准適應症、院內 formulary 與健保給付若會影響執行。

## Guideline 衝突解析

比較每份 guideline 的：

- 臨床問題與目標族群。
- 證據搜尋截止日期與更新機制。
- recommendation strength 與 evidence certainty 的定義。
- 底層研究是否相同、是否納入最新 trial。
- outcome、baseline risk、resource use 與 patient values 假設。
- 專科視角、利益衝突、地區可取得性與醫療體系限制。

若不同推薦來自價值與資源權重，而非事實衝突，直接標示為 decision-context difference。

## 考試與臨床實務分離

考試模式優先回答題目所設定的典型族群、單一最佳答案與教科書門檻。臨床補充只處理：

- 新版指引已改變舊考點。
- 真實病人需要更多條件或例外。
- 題目使用 surrogate、口訣或歷史分類。
- 台灣國考慣例與國際臨床實務不同。

不得以罕見例外否定明確的標準考題，也不得把標準考題簡化直接套到不完整病人資料。
