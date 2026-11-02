# Claude匯入操作與首輪驗收

官方資料查核日：2026-11-02。以下只使用目前官方說明的功能，未宣稱已替使用者完成帳戶操作。

## 最短上手路徑

1. 先把`Claude_快速導入_2026-11-02.md`上傳給Claude，貼上`00_START_HERE.md`的接手訊息。它包含最新指令、個人脈絡、版本裁決、專案狀態與5項完整可攜prompt。另附較小的`Claude_核心匯入包_2026-11-02.zip`，含現行專案必備文件；完整ZIP則保留全部回收原件。
2. 將`01_USER_INSTRUCTIONS_VERBATIM.md`中的使用者原文放進偏好／持續指令。記憶匯入則貼`02_MEMORY_IMPORT.md`內容到Settings → Your Claude／Memory → Start import → Add to memory。匯入後檢查實際保留內容。[官方記憶匯入](https://support.claude.com/en/articles/12123587-import-and-export-your-memory-from-claude)
3. 優先建立「醫師二階」「雪奈原世界線」「新聞與雷達」「音樂與音訊」專案，再按使用需要建立黑色子彈、政治產業、住院臨床助手。每個資料夾有README，列出應上傳的真實檔案與可回查原檔。上傳到專案knowledge並設定project instructions；不要以為只在一段聊天貼連結就等於知識庫已存入。[官方Projects](https://support.claude.com/en/articles/9519177-how-can-i-create-and-manage-projects)
4. 排程照`05_AUTOMATION_MIGRATION.md`建立，先核對資料可用性，再驗內容、自然觸發與實際交付。官方目前說明新排程可在遠端運行；舊本機任務另有保留行為，依帳戶實際界面核對。[官方排程](https://support.claude.com/en/articles/13854387-schedule-recurring-tasks-in-claude-cowork)

ZIP是檔案容器，不是Claude帳戶一鍵還原格式。若介面不能直接解讀ZIP，就先在電腦解壓，上傳快速導入Markdown與各專案README指定檔案。本包沒有要求你逐份重新整理內容。

## 帳戶逐字對話另存

本包已帶走本次可存取的文件、任務與個人脈絡；全帳戶逐字聊天須透過ChatGPT官方匯出。設定→Data controls→Export data→Confirm export，等通知後下載ZIP；官方表示可能需7天，下載連結收到後24小時到期。這部分未由本次檔案工具取得或提交，不能宣稱已包含。[OpenAI官方匯出](https://help.openai.com/en/articles/7260999-exporting-your-chatgpt-history-and-data)

取得後保留原始ZIP；將它作為額外歷史封存，不讓舊對話的過時摘要覆蓋本包已核對的現行文件。

## 首輪可直接貼的驗收題

請依我上傳的實際文件回答，每項附檔名／段落；若檔案未上傳，不得假裝已讀。

1. 我家的核心路由器品牌型號、Mesh子機是什麼？
2. 雪奈十八歲正篇現行版本是什麼？用什麼原檔證據排除舊v17.7摘要？方法學是哪個正式版本？
3. 國考舊錯題總數與各科題數是多少？為什麼135已過時？Q6／Q7、Q26／Q30如何避免再次抄錯？
4. 我11/2的實際作答完成狀態能否確認？有哪些證據才可改成完成？
5. 哪5個任務是啟用、哪些保持停用？手動試跑後能否宣告自動排程正常？
6. 我對「只查證不結論」「只從音檔轉錄」「已給過資訊」與防衛性冗言的要求是什麼？
7. 新聞／體育／遊戲電子的發現與個人化順序是什麼？雷霆有哪些硬性要求？
8. 我的家用車停車重量限制、蕎麥過敏、Carbonara比例與最喜歡的P5R角色各是什麼？
9. 歌單與歷史評分各有多少筆？那些分數是否能當作The Bias List的分數？
10. 你真正已讀哪些文件、已存入哪些記憶、已建立哪些任務？請分開列出，沒執行的不要標成功。

答案基準已在本包，這些題目用來測實際讀取與續接，不是要使用者重述背景。
