# 排程搬移：完整規格、狀態與驗收

本包已保存18個現存任務的完整prompt、原始VEVENT、啟用狀態、ID、更新日期，以及接口能提供的最近一次執行資訊。只將5項啟用任務視為目前要延續的工作。13項停用任務是歷史封存，不自動恢復。

## 目前啟用任務

| 任務 | 使用者時區與時段 | 原系統timing_mode | 截止／差異 |
|---|---|---|---|
| 國考晨間主課表 | Asia/Taipei，每日08:00 | flexible_schedule | 至2027-01-15；現行DTSTART 11/3，原讀書計畫11/2開始 |
| 國考傍晚完成確認 | Asia/Taipei，每日19:00 | flexible_schedule | 至2027-01-15；現行DTSTART 11/2 |
| 工作新聞早午晚報 | Asia/Taipei，08:00／12:00／19:00 | exact_schedule | 長期；原prompt保留三時段 |
| 體育雷達v3 | Asia/Taipei，每日15:00 | exact_schedule | 長期 |
| 遊戲與消費電子雷達 | Asia/Taipei，每日22:00 | flexible_schedule | 長期 |

建立Claude任務時使用`automations/active/`中的 **portable_prompt.md**。同資料夾的 **original_prompt.txt** 是未改寫原文；另有替換對照，保留完整研究規格，只把ChatGPT專屬檔案ID、任務ID與交付位置改成可遷移指示。依當地現在時間設定下一次未來執行，不從歷史DTSTART補跑全部日期。

原始prompt若有舊模型名稱、ChatGPT對話或工具詞，均作歷史規格看待；不能承諾Claude能鎖定那些模型。新平台選可用的深度推理配置，採同一份交付驗收。

## 可直接交給Claude的部署要求

請讀本包5項active任務的完整portable_prompt與exported_tasks.json，建立同功能排程。新聞若不支援一個任務三時段，可拆成晨／午／晚三個，總共7個任務；共用新聞State檔避免重複與失憶。其他任務仍各一個。請以Asia/Taipei列出你實際建立的任務ID、下次執行時間、時區與資料位置。國考兩項到2027-01-15結束，且08:00與19:00使用明確鐘點設定；遊戲電子保留原Flexible偏好，若平台只有固定時鐘，註明映射結果。

排程必須能讀到雲端可用的專案檔與持續更新的狀態；不能只引用ChatGPT Library URL或本機不存在的路徑。需要的知識檔請先加入Claude專案，才建立依賴它的任務。使用者若已回報今日進度，先合併，禁止再問已知資訊。

**本次交接沒有登入Claude或建立Claude任務，也沒有停用ChatGPT任務。** 上述是已準備好的部署指令，不能標成部署成功。

## 驗收分開記錄

1. **設定驗收**：任務ID、時區、時段、期限、啟用狀態、下一次時間；全文prompt無截斷，來源與持續狀態可存取。
2. **內容試跑**：手動run輸出完整、來源正確、能更新狀態。紀錄trigger=manual，只證明內容路徑可用。
3. **自動觸發**：等待自然到期的scheduler run，保存scheduled_for、started_at、run ID、能取得的trigger證據；期間不手動啟動同一任務混淆來源。
4. **交付驗收**：使用者能在指定位置看到完整產出，確認沒有空白／被截斷／只顯示工作流程。通知、生成與畫面可見性分別記錄。
5. **續接驗收**：第二次run能讀上次已寫入的State及使用者回報，作出真實差分；國考不重派已完成批次。

如果平台不暴露trigger欄位，就明確記錄能驗到的項目，不發明日誌。當使用者要求關閉舊任務時，再按其指示操作；不要自行刪除帳戶、取消訂閱或清空歷史。

## 執行狀態資料

新平台建議每次寫入：task_id、run_id、scheduled_for、started_at、completed_at、trigger_source、result_path、delivery_verified、content_complete、source_cutoff、state_version。值不知道就null，不能用scheduled_for推定trigger。模板在`automations/RUN_LOG_TEMPLATE.csv`。

國考需獨立保存答案、把握度、訂正日期與到期回收；新聞、體育、電子各自保存候選池、已報事件與變化，互不混用。初始State不得把歷史摘錄中的未知內容補成已報。
