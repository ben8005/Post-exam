# 上線部署指南

整個網站是純靜態檔案，三種免費方式任選一種。本機 git repo 已初始化並完成第一次提交。

---

## 方法 A：Cloudflare Pages（最簡單，免帳號綁卡、不用 git）

1. 到 https://pages.cloudflare.com → 註冊／登入。
2. 選 **Upload assets**（直接上傳，不用 GitHub）。
3. 把 `C:\Users\YU\post-exam` 整個資料夾的內容拖進去上傳。
4. 完成後會得到一個網址，例如 `https://郵局考古題.pages.dev`。

> 之後更新題目：重新上傳一次資料夾即可。

---

## 方法 B：Netlify Drop（拖曳即上線，連註冊都可略過試用）

1. 到 https://app.netlify.com/drop
2. 把 `post-exam` 整個資料夾直接拖進網頁。
3. 立刻得到一個網址。要保留網址再註冊登入即可。

---

## 方法 C：GitHub Pages（適合長期維護、用 git 更新）

需要一個 GitHub 帳號。步驟：

1. 在 https://github.com/new 建一個新的 repository（例如 `post-exam`，設為 Public 或 Private 皆可）。
2. 在本資料夾執行（把 `你的帳號` 換成實際帳號）：

   ```bash
   cd C:\Users\YU\post-exam
   git branch -M main
   git remote add origin https://github.com/你的帳號/post-exam.git
   git push -u origin main
   ```

3. 到該 repo 的 **Settings → Pages**：
   - Source 選 **Deploy from a branch**
   - Branch 選 **main**、資料夾選 **/ (root)** → Save
4. 等 1–2 分鐘，網址會是 `https://你的帳號.github.io/post-exam/`。

> 之後更新題目：改完 `data/questions.js` 後
> `git add -A && git commit -m "更新題庫" && git push`，網站會自動更新。

---

## 上線後在手機使用（PWA）

用手機瀏覽器開啟網址 → 瀏覽器選單 → **加入主畫面**。
之後就像 App 一樣，可離線練習（圖示為綠底白「郵」字）。

---

## 注意

- 若設為公開網站，請確認題目／詳解沒有侵犯他人（補習班）的版權。自用或私下分享通常沒問題。
- 學習紀錄存在「使用者各自的瀏覽器」，不會上傳，也不會跨裝置同步。
