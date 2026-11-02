# Custom Library Skills Router

> **唯一入口：**本檔是 `/Skills` 內所有檔案庫自訂 Skill 的統一路由表。這些檔案不是系統原生 Skill，也不是外掛。讀取本檔後，應在**目前對話**中依下列規則主動選擇並實際讀取對應檔案。

- Router version: 1.0
- Updated: 2026-07-31 (Asia/Taipei)
- Collections: Charles + Matt Pocock

## 1. Router contract

讀取本檔後，在目前對話的後續任務中：

1. 先判斷任務是否匹配本 registry 的 Skill；匹配時，**先讀取精確路徑的 Skill 檔案，再執行任務**。
2. 不得只依 Skill 名稱、本 README 摘要或模型既有印象模仿流程。
3. 不得用系統原生 Skill／外掛 Skill 搜尋，取代對檔案庫 `/Skills` 的搜尋與讀取。
4. 同一 Skill 在同一對話中已完整讀取，且檔案未更新時，可沿用；遇到高風險任務、使用者要求強制重載或版本可能變動時，重新讀取。
5. 多個 Skill 同時適用時，只載入會實質改變流程的**最小集合**，並依「外層流程 → 領域流程 → 證據／方法依賴」排序。
6. 使用者明確指定檔案庫 Skill 時優先採用；若與更高層級指令、工具能力、安全限制或使用者真正目標衝突，應說明並採可執行替代方案。
7. Skill 內要求目前環境不存在的能力（例如背景代理、未連接的工具或缺失的輔助檔）時，不得假裝完成；應同步執行可行部分或明確說明限制。
8. 未匹配任何 Skill 時正常回答，不強行套用。

### 啟動方式

新對話最短啟動句：

```text
載入檔案庫 /Skills/README.md，並在本對話中啟用自訂 Skill routing。
```

使用者也可直接指定：

```text
檔案庫 skill: independent-reassessment
檔案庫 skills: independent-reassessment + source-backed-analysis
```

「檔案庫 skill(s)」必須解讀為本 README 所列檔案，不是系統原生 Skill。

## 2. Activation modes

- **Auto**：任務明確匹配時，主動讀取並使用。
- **Explicit**：通常只有使用者明確要求該產物／流程時使用；不可因語意相近就擅自執行寫檔、提交、建立工單或大型工作流。
- **Dependency**：不單獨路由；由主 Skill 要求時讀取。
- **Router**：只負責選擇流程，不是主要執行 Skill。
- **Metadata**：來源與版本紀錄，不作為任務流程。

## 3. High-priority routing rules

### 3.1 查證與重評

- 使用者質疑既有答案、說「你確定嗎／為什麼漏掉／重新檢討／查證／事實查驗／審計」或提出反駁：
  - 外層：`independent-reassessment`
  - 涉及外部可驗證事實、現況或來源：再載入 `source-backed-analysis`
- 一般最新資訊、新聞、產品、公司、政策、人物、外部資料比較或因果分析：`source-backed-analysis`
- 重評時先判定質疑為「成立／部分成立／不成立／證據不足」，不得預設原答案錯或使用者反駁對。

### 3.2 醫療

- 診斷、治療、預後、用藥、指引、病人特定問題或考試答案與實務差異：`clinical-evidence-review`
- 醫療回答遭質疑：`independent-reassessment` → `clinical-evidence-review`；需要外部證據時由其搭配 `source-backed-analysis`
- `evidence-taxonomy` 與 `clinical-evidence-reference` 為依賴文件。

### 3.3 裝置與軟體故障

- 手機、平板、PC、路由器、網路、音訊鏈、周邊、充電、電源、散熱、連線或間歇性裝置問題：`device-diagnostics`
- 程式碼、服務、測試、例外、效能回歸等軟體工程 bug：`diagnosing-bugs`
- 裝置診斷遭質疑：`independent-reassessment` → `device-diagnostics`
- 涉及規格、韌體、驅動、相容性或已知問題：再搭配 `source-backed-analysis`

### 3.4 研究分流

- 公開世界的現況、新聞、產品、規則與外部主張：`source-backed-analysis`
- 在程式專案中查官方文件、API、規格或原始碼，並把結果寫回 repo：`research`
- 不可因名稱相同，把工程 `research` 當成一般網路查證流程。

### 3.5 Handoff 分流

- 一般 ChatGPT 對話要搬到新對話、保留最小充分狀態：`conversation-handoff`
- 工程 workspace／repo 要交給另一個 agent 或 session：`handoff`
- 兩者皆為 Explicit；只有使用者要求交接、冷啟動包或新對話續接時才執行。

### 3.6 構想到交付的工程主流程

有 codebase 的功能／設計工作，視需要採最小子流程：

```text
grill-with-docs → domain-modeling → prototype（可選）
→ to-spec（多 session 或需正式規格）
→ to-tickets（需拆工）
→ implement → tdd（適用時） → code-review
```

- 沒有 codebase，只想把想法問清楚：`grill-me`／`grilling`
- 工作巨大、決策路徑超過單一 session：`wayfinder`
- 不確定工程流程：`ask-matt` 可作次級 Router，但本 README 是檔案庫的第一層 Router。

## 4. Unified skill registry

### 4.1 Evidence, clinical, diagnostics, continuity

| Skill | Mode | Exact path | Use when |
|---|---|---|---|
| `independent-reassessment` | Auto | `/Skills/Charles/independent-reassessment.md` | 獨立重評既有答案、使用者反駁、重大遺漏或來源質疑。 |
| `source-backed-analysis` | Auto | `/Skills/Charles/source-backed-analysis.md` | 當前或重要外部主張、指定來源、證據式比較、因果與歸因分析。 |
| `clinical-evidence-review` | Auto | `/Skills/Charles/clinical-evidence-review.md` | 醫療、診斷、治療、預後、用藥、指引、病人特定或考試／實務分流。 |
| `device-diagnostics` | Auto | `/Skills/Charles/device-diagnostics.md` | 消費電子、網路、音訊、硬體／軟體裝置問題的故障隔離。 |
| `conversation-handoff` | Explicit | `/Skills/Charles/conversation-handoff.md` | 為新 ChatGPT 對話建立最小充分冷啟動包。 |

### 4.2 Engineering

| Skill | Mode | Exact path | Use when |
|---|---|---|---|
| `ask-matt` | Router / Explicit | `/Skills/Matt Pocock/engineering-ask-matt.md` | 不確定 Matt Pocock 工程 Skill 或 flow 的選擇。 |
| `code-review` | Auto | `/Skills/Matt Pocock/engineering-code-review.md` | 審查 branch／PR／自固定點以來的 diff，核對 standards 與 spec。 |
| `codebase-design` | Auto / Dependency | `/Skills/Matt Pocock/engineering-codebase-design.md` | 設計深模組、介面、seam、可測試性或 AI 可導航性。 |
| `diagnosing-bugs` | Auto | `/Skills/Matt Pocock/engineering-diagnosing-bugs.md` | 困難程式 bug、測試失敗、例外或效能回歸的診斷迴圈。 |
| `domain-modeling` | Auto | `/Skills/Matt Pocock/engineering-domain-modeling.md` | 建立／修正領域術語、ubiquitous language、CONTEXT 或 ADR。 |
| `grill-with-docs` | Explicit | `/Skills/Matt Pocock/engineering-grill-with-docs.md` | 在 codebase 中以逐題訪談釐清設計，並同步留下 glossary／ADR。 |
| `implement` | Explicit | `/Skills/Matt Pocock/engineering-implement.md` | 依 spec 或 tickets 實作、驗證、review 與提交工作。 |
| `improve-codebase-architecture` | Explicit | `/Skills/Matt Pocock/engineering-improve-codebase-architecture.md` | 掃描 codebase 的 deepening opportunities 並產生架構改善報告。 |
| `prototype` | Auto | `/Skills/Matt Pocock/engineering-prototype.md` | 用可拋棄 prototype 回答狀態模型、邏輯或 UI 方向問題。 |
| `research` | Auto | `/Skills/Matt Pocock/engineering-research.md` | 專案內以一手技術來源研究 docs／API／規格／原始碼並寫入 repo。 |
| `resolving-merge-conflicts` | Auto | `/Skills/Matt Pocock/engineering-resolving-merge-conflicts.md` | 處理進行中的 git merge／rebase conflict。 |
| `setup-matt-pocock-skills` | Explicit | `/Skills/Matt Pocock/engineering-setup-matt-pocock-skills.md` | 首次在 repo 建立 issue tracker、triage vocabulary 與 domain docs 配置。 |
| `tdd` | Auto | `/Skills/Matt Pocock/engineering-tdd.md` | 使用 red–green–refactor、test-first 或整合測試開發。 |
| `to-spec` | Explicit | `/Skills/Matt Pocock/engineering-to-spec.md` | 將既有討論整理成 spec／PRD 並發布到專案 tracker。 |
| `to-tickets` | Explicit | `/Skills/Matt Pocock/engineering-to-tickets.md` | 將 plan／spec 拆成 tracer-bullet tickets 與 blocking edges。 |
| `triage` | Explicit | `/Skills/Matt Pocock/engineering-triage.md` | 對 issue／外部 PR 分類、驗證、追問並形成 agent-ready brief。 |
| `wayfinder` | Explicit | `/Skills/Matt Pocock/engineering-wayfinder.md` | 超過單一 agent session 的大型工作，以 decision tickets 建立決策地圖。 |

### 4.3 Productivity and learning

| Skill | Mode | Exact path | Use when |
|---|---|---|---|
| `grill-me` | Explicit | `/Skills/Matt Pocock/productivity-grill-me.md` | 沒有 codebase 時，以逐題訪談把計畫或設計問清楚。 |
| `grilling` | Auto | `/Skills/Matt Pocock/productivity-grilling.md` | 使用者要求壓力測試想法、反覆追問或使用 grill 類觸發語。 |
| `handoff` | Explicit | `/Skills/Matt Pocock/productivity-handoff.md` | 工程 workspace／agent session 之間建立交接文件。 |
| `teach` | Explicit | `/Skills/Matt Pocock/productivity-teach.md` | 在 workspace 中建立可跨 session 延續的系統化教學專案。 |
| `writing-great-skills` | Dependency / Explicit | `/Skills/Matt Pocock/productivity-writing-great-skills.md` | 撰寫、審查或改進 Skill 的可預測性、觸發與流程設計。 |

## 5. Dependency and metadata files

下列檔案不可取代主 Skill，也不應單獨自動路由；由主 Skill 需要時讀取：

| Type | Exact path | Role |
|---|---|---|
| Dependency | `/Skills/Charles/evidence-taxonomy.md` | Charles 證據類別、狀態、來源角色與信心標籤的權威定義。 |
| Dependency | `/Skills/Charles/clinical-evidence-reference.md` | `clinical-evidence-review` 的臨床證據與方法參考。 |
| Dependency | `/Skills/Charles/device-diagnostics-reference.md` | `device-diagnostics` 的診斷參考。 |
| Dependency | `/Skills/Charles/conversation-handoff-reference.md` | `conversation-handoff` 的分支參考。 |
| Metadata | `/Skills/Matt Pocock/README.md` | 上游快照說明；不是本檔案庫的路由入口。 |
| Metadata | `/Skills/Matt Pocock/MANIFEST.md` | 上游來源、版本與雜湊清單。 |

Matt Pocock 快照未包含部分相對連結指向的輔助檔（模板、glossary、tests、scripts 等）。遇到缺失檔案時：

1. 先確認該檔是否真的不在 Library／repo。
2. 不得臆造其內容。
3. 若主流程仍可安全執行，依現有內容做最小適配並標示缺口；否則說明阻塞。

## 6. Priority and conflict rules

1. 更高層級平台／系統／安全規則永遠優先。
2. 使用者明確指定的檔案庫 Skill 優先於自動路由。
3. 高風險領域 Skill 優先於通用 Skill：例如醫療用 `clinical-evidence-review`，不可只用一般來源分析。
4. `independent-reassessment` 只在重評既有答案或反駁時作為最外層。
5. `source-backed-analysis` 負責外部證據鏈，不取代醫療、裝置或工程領域流程。
6. `device-diagnostics` 處理裝置／系統層問題；`diagnosing-bugs` 處理 codebase 內可重現的程式故障。
7. Charles `conversation-handoff` 與 Matt `handoff` 不可混用：前者是一般新對話冷啟動，後者是工程 workspace／agent 交接。
8. 一般公開資訊研究優先 `source-backed-analysis`；工程 repo 內產出研究文件才用 `research`。
9. 任何會寫檔、提交、建立／修改 issue、PR 或 tracker 狀態的 Explicit Skill，只有在使用者要求該動作時執行。
10. Skill 內容與使用者當前要求衝突時，以使用者當前要求為準，但保留必要的安全與證據門檻。

## 7. Composition examples

```text
重評一般外部事實
independent-reassessment → source-backed-analysis → evidence-taxonomy
```

```text
重評醫療回答
independent-reassessment → clinical-evidence-review
                         → source-backed-analysis（需外部查證時）
                         → evidence-taxonomy / clinical-evidence-reference
```

```text
裝置故障且涉及韌體／相容性
 device-diagnostics → source-backed-analysis
```

```text
程式 bug
 diagnosing-bugs → tdd（修復需要 test-first 時） → code-review
```

```text
大型功能
 grill-with-docs → domain-modeling → prototype（可選）
 → wayfinder 或 to-spec → to-tickets → implement → tdd → code-review
```

## 8. Completion signal

載入本檔時，只需簡短確認：

```text
已載入 /Skills/README.md；本對話將主動路由並在使用前實際讀取相符的檔案庫 Skill。
```

不必逐項重述 registry。後續回答也不必反覆宣告使用了 Skill，除非使用者要求、需要說明方法，或檔案／能力限制影響結果。
