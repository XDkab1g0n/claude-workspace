# Conversation Handoff — Branch Reference

本檔只在 `conversation-handoff` 已鎖定續接目標後使用。只讀取與下一個對話相符的分支；各分支補充要攜帶的狀態，不改變主 skill 的 cold-start test。

## Research / current information

- 記錄查證截止時間及相關地區、市場、版本或司法管轄。
- 分開事件發生日、來源發布日、最後更新日與回答當時狀態。
- 標記價格、規格、政策、供應、排名、兌換碼、人物職位等需刷新資訊。
- 保存關鍵來源鏈與實質反證；不把暫時推論記成已確認。
- 建議使用 `source-backed-analysis`；重審既有回答時外加 `independent-reassessment`。

## Device diagnostics

- 記錄精確症狀契約、型號與版本、拓撲、狀態向量及安全限制。
- 保存最小重現、pass/fail 對照、間歇問題重現率與量測基線。
- 每項已完成測試記錄：變數、預測、結果、對假設排序的影響。
- 分開根因、最可能故障層、workaround 與尚未決定的硬體故障。
- 下一個動作指定單一資訊增益最高的測試。
- 建議使用 `device-diagnostics`。

## Clinical

- 只攜帶達成任務所需的最少病人資料，移除姓名、病歷號、地址、電話及非必要日期等識別資訊。
- 記錄問題模式：考試、一般知識、臨床決策、病人特定或文件審查。
- 保存臨床問題框架、重要 outcome、證據確定性、適用性及會逆轉決策的缺失資料。
- 藥物問題記錄已知的 indication、dose basis、腎肝功能、交互作用、過敏、妊娠及監測條件；未知保持未知。
- 標記指引、仿單、警示與當地給付資訊的版本日期。
- 建議使用 `clinical-evidence-review`；醫療回答被質疑時外加 `independent-reassessment`。

## Writing / creative work

- 記錄作品目的、受眾、格式、語氣、敘事視角與長度限制。
- 保存 canonical facts、世界觀規則、人物當前狀態與時間線。
- 區分已採用版本、仍在比較的草案與已否決方向。
- 引用完整稿件或設定檔，不在交接文件重複全文。
- 指定下一個要完成的場景、段落、修訂或決策，而非籠統寫「繼續寫」。

## Analysis / decision

- 記錄決策問題、比較集合、評價標準、權重與成功條件。
- 保存真正影響選擇的 trade-offs，而不只保存最終排名。
- 區分已確認資料、估計、假設與價值權重。
- 記錄已選方案的 rationale、適用範圍及 reopen trigger。
- 資料可能變動時建議使用 `source-backed-analysis`。

## File or artifact production

- 記錄輸出格式、檔名、尺寸、頁數、工作表／投影片／章節結構及模板要求。
- 保存已完成檔案的確切位置與驗證狀態。
- 記錄尚未完成或失敗的轉換、格式、公式、渲染與品質檢查。
- 只有實際存在於執行環境的檔案才能使用 `sandbox:/mnt/data/`；Library 與 connector 檔案使用其可解析引用。

## Code or repository work

- 記錄 repo、branch、commit／PR／issue、工作目錄與已修改檔案。
- 保存建置、測試、lint、CI 的精確命令及最近結果。
- 引用 spec、ADR、ticket、diff 或 review，不重複其完整內容。
- 記錄未提交變更、衝突、阻塞及下一個原子操作。
- 只有當新對話確實能存取 repository 或 connector 時才把其設為必要輸入。
