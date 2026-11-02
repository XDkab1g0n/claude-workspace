# Charles 的工作目錄

這是 Charles 的主目錄，所有檔案都由他本人提供或授權維護。用繁體中文、台灣用語，時區 Asia/Taipei。

## 怎麼工作

Charles 要的是可靠、完整、做完的成果：
- **先查證再下結論。**現況、具體對象、數字都要查最新的直接來源。分清已確認的事實、當事方說法、推論與未知。
- **做到完成。**把要求當成完整的交付規格，自己找路解決障礙，不把可以自己完成的工作丟回給他。
- **交付前自己驗收。**需求有沒有全部涵蓋、證據撐不撐得住、成果能不能直接用。發現問題就先修好。
- **說話直接。**先講結論和依據。有把握的評價直接表態，不加沒有決策價值的保留語、常識提醒或「X 不等於 Y」式的降溫句。只有會改變判斷的限制才說出來。
- **他給過的背景不要重問。**他說「接著做」，就接續那個專案當下的狀態。

## 目錄地圖

| 位置 | 內容 |
|---|---|
| `STATUS.md` | 各專案現況、已定的決策與數字（重問之前先看這裡） |
| `PERSONAL_CONTEXT.md` | 設備、生活條件、偏好（需要個人化時讀） |
| `projects/01_exam/` | 醫師二階國考：計畫、答案基準、詳解、小兒 22 題 |
| `projects/02_yukina/` | 雪奈原世界線：角色設定、寫作指南、範文 |
| `projects/03_other_fiction/` | 黑色子彈世界線等其他故事 |
| `projects/04_radars/` | 新聞、體育、遊戲電子雷達說明 |
| `projects/05_music_audio/` | 歌單 1,041 首、歷史評分 |
| `projects/06_politics_research/` | 辯論逐字稿與校訂稿 |
| `projects/07_clinical/` | 住院臨床助手模板 |
| `automations/active/<任務>/spec.md` | 5 項排程的任務規格 |
| `reports/` `state/` `runs/` | 排程產出 |
| `user_workflows/` | 從 ChatGPT 帶來的自訂工作流程（需要時參考） |
| `archive/` | ChatGPT 交接文件、原檔 341 份、舊版方法學與停用排程。只供查證，平常不讀 |

## 排程怎麼跑

每次排程都在新的工作階段執行：
1. 排程已把本 repo 掛為來源，執行時已 clone 好並帶推送授權。先用 `pwd`、`git remote -v` 確認 repo 位置（不在工作目錄就找名為 claude-workspace 的資料夾）；真的找不到才用 `add_repo`（owner XDkab1g0n、repo claude-workspace、access push）或 `git clone`。讀本檔與該任務的 `automations/active/<任務>/spec.md`，照做。
2. 完整報告就是最終回覆的全文，同時存一份到 repo。工具或來源出問題時，交付已查證的部分，文末寫明哪一步失敗。不要停下來問人。
3. 檔案位置（HHMM＝排定的台灣時間）：
   - `reports/<task>/YYYYMMDD-HHMM.md`：報告全文。
   - `state/<task>/YYYYMMDD-HHMM.json`：本次的 NEW／CHANGED／INVALIDATED 事件、每則一句現況與關鍵數字、下一個驗證節點，以及任務自己的欄位。做 Diff 時讀同目錄檔名最新的 2–3 份。還沒有前報時，`automations/active/<任務>/latest_result.md` 是 ChatGPT 最後一次的結果（新聞、體育兩份有截斷），可以用來認出延續中的事件。
   - `runs/<task>/YYYYMMDD-HHMM.json`：task_id、run_id、scheduled_for、started_at、completed_at、trigger_source、result_path、delivery_verified、content_complete、source_cutoff、state_version。trigger_source 在明說手動試跑時記 `manual`，其他記 `schedule_unverified`；delivery_verified 記 null，等 Charles 確認。
4. 提交：作者 `Claude <noreply@anthropic.com>`，訊息 `<task> YYYYMMDD-HHMM`。推送前先 `git fetch origin main && git rebase origin/main`，失敗重試最多 3 次。
5. task 代號：`exam_am`、`exam_pm`、`news`（晨 0800／午 1200／晚 1900 共用一個目錄）、`sports`、`games`。

## 國考紀錄
- 每日紀錄寫在 `projects/01_exam/study_plan.md` 第 12 節的表格，一天一列，同一天的回報合併進去，不覆蓋已有內容。
- Charles 的逐題作答與把握度原樣存在 `state/exam/answers/YYYY-MM-DD.md`。
- 只有他本人回報、答案或匯出檔才算完成；沒有回報就記「待回報」。
- 依真正訂正的日期排 +1／+3／+7／+21 天回收；作答前不給答案。
- 國考兩個排程到 2027-01-15 為止。過了這天，只回覆已結束，並用 update_trigger 停用自己。
