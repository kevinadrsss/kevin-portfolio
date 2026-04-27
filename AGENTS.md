# AGENTS.md — Kevin Portfolio 專案工作規則

這個檔案是給 Codex、Claude Code、或其他 coding agent 讀的專案說明。
請優先遵守這裡的規則，再開始修改檔案。

另請讀取：
- `CODEX.md` — 阿福 / Hermes 工作模式摘要

## 專案身份

這是 Kevin Chen / 陳品愷的個人作品集網站。

網站目的：
- 展示 Motion Design、3D Visual、AI Workflow、Creative System 能力
- 讓中文訪客與外國訪客都看得懂
- 作為求職、接案、合作邀約使用

目前網站是純靜態網站，部署在 GitHub Pages。

Live site:
- https://kevinadrsss.github.io/kevin-portfolio/

GitHub repo:
- https://github.com/kevinadrsss/kevin-portfolio

## 重要檔案與資料夾

主要入口：
- `index.html`

靜態素材：
- `images/` — 圖片與縮圖
- `gifs/` — 電視牆 GIF 預覽
- `videos/` — 影片素材
- `.nojekyll` — GitHub Pages 靜態部署用，保留

不要任意刪除：
- `images/`
- `gifs/`
- `videos/`
- `.nojekyll`

不要提交：
- `.git/`
- `.gifenv/`
- `index.backup-*.html`
- 暫存檔、測試輸出、個人本機路徑

## 技術架構

目前是單頁靜態 HTML：
- HTML / CSS / Vanilla JavaScript 都在 `index.html`
- 沒有 build step
- 沒有 npm / Vite / React
- 修改後可直接用瀏覽器開 `index.html` 預覽

語言切換：
- 右上角有中英切換按鈕
- 預設中文
- `?lang=en` 可直接開英文版
- 使用 `data-i18n` / `data-i18n-html` 和 JS translations 物件切換文字
- 新增文案時，務必同時補中文與英文

電視牆：
- 使用 GIF，不用大量 autoplay video
- 目的：提高相容性，避免瀏覽器或公司電腦不播放影片
- 電視牆素材位於 `gifs/`
- 第三列目前是「最新作品」

## Kevin 偏好

語言：
- 對 Kevin 回覆用繁體中文
- 網站文案可中英雙語

文案風格：
- 不要太制式
- 不要空泛品牌詞，例如「創新、賦能、全方位」
- 技術內容也要讓非工程師看得懂
- 強調 Kevin 能把 AI、3D、影片與工作流整成可落地的創作系統

網站風格：
- 深色、科技感、紫色 / 青色霓虹視覺
- 不要改成白底企業模板
- 保持個人作品集感，不要像制式履歷

## 修改規則

修改前：
1. 先讀 `index.html`
2. 確認目前區塊結構
3. 不要大改架構，除非任務明確要求

修改時：
1. 優先做小而穩的改動
2. 保持現有視覺語言
3. 新增中文文案時，同步新增英文翻譯
4. 新增素材時，使用相對路徑，例如 `gifs/example.gif`
5. 不要使用 Windows 絕對路徑，例如 `C:\...` 或 `G:\...`
6. 不要把 API key、token、私人設定寫進網站

修改後必做：
1. 檢查 `index.html` 是否能正常開啟
2. 測試中文模式
3. 測試英文模式：`?lang=en`
4. 確認瀏覽器 console 沒有 JS error
5. 確認圖片 / GIF / 影片沒有破路徑
6. 再 commit

## Git 工作流

目前主分支：
- `main`

常用流程：
```bash
git status --short
git add index.html images gifs videos .nojekyll AGENTS.md
git commit -m "Describe the change"
git push origin main
```

如果在 WSL 裡推 GitHub 失敗，可以改用 Windows Git：
```bash
'/mnt/c/Program Files/Git/cmd/git.exe' push origin main
```

GitHub Pages 部署後，驗證：
```text
https://kevinadrsss.github.io/kevin-portfolio/?v=YYYYMMDD
```

如果頁面看起來沒更新，通常是快取。
使用 cache-busting query，例如：
```text
?v=20260427bilingual
```

## 隱私與安全

網站目前公開資訊包含 email 和電話。
不要新增更多私人資料，除非 Kevin 明確要求。

不要提交：
- OAuth token
- API key
- Google Drive 私人設定
- 對話全文
- 系統記憶原文
- `.env`
- `client_secret*.json`

如果任務涉及外部 repo、插件、MCP、CLI 工具，先做安全審查：
1. Repo 本體風險
2. 執行層風險
3. 是否會讀檔、發網路、碰憑證、修改第三方服務

## 備份與打包

網站打包備份目前放在：
- `C:\Users\User\Desktop\portfolio_packages\`
- `G:\我的雲端硬碟\Kevin_Portfolio_Backups\`

打包時應包含：
- `index.html`
- `.nojekyll`
- `images/`
- `gifs/`
- `videos/`

打包時排除：
- `.git/`
- `.gifenv/`
- `index.backup-*.html`
- 暫存檔

## 給 Agent 的一句話

你不是在做通用模板網站。
你是在維護 Kevin 的個人作品集：一個結合 Motion Design、3D、AI Workflow、創作系統化的展示頁。
請保持它有個性、能展示作品、讓中文和英文訪客都能快速理解 Kevin 的價值。
