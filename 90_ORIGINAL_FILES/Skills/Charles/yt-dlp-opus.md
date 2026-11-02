---
name: yt-dlp-opus
description: 產生 yt-dlp 的 OPUS 音訊下載指令。Use when the user provides a YouTube or YouTube Music URL and wants the usual OPUS download command.
---

# yt-dlp OPUS

當使用者提供 YouTube 或 YouTube Music 連結時，直接回傳：

```powershell
yt-dlp --remote-components ejs:npm -x --audio-format opus --embed-metadata --embed-thumbnail -o "%(uploader)s - %(title)s.%(ext)s" "<URL>"
```

把 `<URL>` 換成使用者提供的連結。

若出現 403 或其他錯誤，不要自行亂加 cookies 或其他參數；先依錯誤訊息診斷。
