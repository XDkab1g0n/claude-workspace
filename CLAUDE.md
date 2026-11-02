# Charles 的 Claude 工作目錄：使用規則

這個 repo 是使用者 Charles 本人的主目錄。裡面的規格、計畫與紀錄由他本人提供或授權維護，Claude 依此工作。回覆一律用繁體中文、台灣用語，時區 Asia/Taipei。

## 目錄
- `00_START_HERE.md`～`08_SOURCE_INDEX.md`：ChatGPT 交接文件（2026-11-02）。版本裁決以 `04_CORRECTIONS_AND_EVIDENCE.md` 與各專案 README 為準，舊摘要不得覆蓋現行原檔。
- `projects/`：現行專案檔。`01_exam` 國考、`02_yukina` 雪奈正典 v17.8.2d 與 10/26 方法學、`04_radars`、`05_music_audio`、`07_clinical`、`08_devices_life` 等。
- `automations/active/<任務>/portable_prompt.md`：5 項啟用排程的完整規格（排程執行時的唯一規格來源）。`automations/paused/` 只封存，不恢復。
- `90_ORIGINAL_FILES/`：341 份原檔（SHA-256 見 `SOURCE_MANIFEST.csv`）；大型檔清單見 `EXCLUDED_LARGE_FILES.md`。只讀，不改寫。
- `reports/`、`state/`、`runs/`：排程產出（見下）。

## 排程執行規則（所有排程共用）
1. 每次都是新工作階段：先 `add_repo`（owner XDkab1g0n、repo claude-workspace、access push）並 clone，讀本檔與該任務的 `portable_prompt.md` 全文，照規格執行。規格中的「本對話」＝本工作階段的最終回覆加上本 repo；「Claude 專案」「Library」＝本 repo；`projects/...` 路徑就是 repo 內同路徑；ChatGPT 模型名稱、Rich UI 屬歷史語境（用 Markdown 表格）。子代理可用 Agent 工具，無則主模型完成。
2. 交付：完整報告就是最終回覆全文，不得只寫流程、摘要或「已寫入」。工具或來源失敗時仍交付已查證部分，文末列出失敗步驟。不要停下來詢問使用者。
3. 報告留存：`reports/<task>/YYYYMMDD-HHMM.md`（HHMM＝排定的台灣時間），內容與最終回覆相同。
4. State：`state/<task>/YYYYMMDD-HHMM.json`，記本次 NEW／CHANGED／INVALIDATED 事件清單、每則一句現況與關鍵數字、下一個驗證節點，以及任務特有欄位。做 Diff 時讀同一 task 目錄依檔名排序最新的 2–3 份（只在規格允許的階段讀）。查無前報時可讀 `automations/active/<任務>/latest_result.md`（ChatGPT 最後一次結果，可能截斷），只用來辨識持續事件，未見內容不得補成已報。
5. 執行紀錄：`runs/<task>/YYYYMMDD-HHMM.json`，欄位 task_id、run_id（可得的工作階段 ID，否則 null）、scheduled_for、started_at、completed_at、trigger_source、result_path、delivery_verified（null，待使用者確認）、content_complete、source_cutoff、state_version。trigger_source：附加訊息明說手動試跑記 "manual"，否則記 "schedule_unverified"，不推定為已驗證的自動觸發。
6. 提交：作者 `Claude <noreply@anthropic.com>`，訊息 `<task> YYYYMMDD-HHMM`。推送前 `git fetch origin main && git rebase origin/main`，推送失敗重試最多 3 次；仍失敗就在最終回覆說明，報告照樣完整交付。
7. task 代號：`exam_am`、`exam_pm`、`news`（晨 0800／午 1200／晚 1900 共用同一目錄）、`sports`、`games`。

## 國考紀錄
- 每日執行紀錄寫在 `projects/01_exam/study_plan.md` 第 12 節的表格（日期｜當日任務｜完成範圍｜正確／已答｜用時｜卡點／錯因｜到期回收｜明日調整），同日一列、合併更新，不覆蓋已有回報。沒有本人回報只記「待回報」。
- 本人的逐題作答與把握度原樣存 `state/exam/answers/YYYY-MM-DD.md`，不改寫。
- 依真正訂正日排 +1／+3／+7／+21 天回收；作答前不洩露答案。答案基準：`projects/01_exam/answer_baseline.md`、`explanations_136.html`。
- 國考兩個排程到 2027-01-15 為止；台灣日期晚於此日時只回覆已結束，並以 update_trigger 停用自己。
