# 應用數學 AI 作業網站

網址：https://2007-sunny.github.io/applied-mathematics-homework/

Google Sites 的「嵌入程式碼」不會執行 KaTeX，公式會顯示成原始碼。所以網頁先放到 GitHub Pages，再用 Google Sites 的「嵌入 → 依網址」把 GitHub Pages 的網址嵌進去。

## 資料夾

```
AI作業網站/                  ← 這整個資料夾就是 GitHub repo
├─ index.html               網站首頁，列出每次作業（新增作業要加一張卡片）
├─ README.md                本檔
├─ _範本/
│   ├─ 範本.html             新網頁從這裡複製：KaTeX、中英切換、深淺色、canvas 高度都處理好了
│   └─ prompt範本.md         給 AI 的 vibe coding prompt（含 6 條規範與踩過的坑）
├─ hw3_ch5/                 第三次 AI 作業（Ch5 §5.1–5.7）
│   ├─ page1.html            §5.1–5.2 空間與權重
│   ├─ page2.html            §5.3–5.7 微分算符的結構
│   └─ 第一頁_prompt.md、第二頁_prompt.md
└─ 第一頁_空間與權重.html、第二頁_微分算符的結構.html
                             舊網址，只做自動轉址到 hw3_ch5/，不要刪
```

網頁檔名用英文（`hwN_chX/pageN.html`），網址才不會變成一長串 `%E7%AC%AC…`。

## 下次作業的流程

1. 開新資料夾 `hw4_chX/`。
2. 用 `_範本/prompt範本.md` 寫 prompt，到 claude.ai 或 Gemini 做網頁，保存「AI 討論」和「Vibe Code」的分享連結。
3. 把做好的 HTML 存成 `hw4_chX/page1.html`、`page2.html`（或從 `_範本/範本.html` 改）。
4. 在 `index.html` 加一張卡片連到新頁面。
5. 推上 GitHub：
   ```bash
   git add -A
   git commit -m "第四次 AI 作業"
   git push
   ```
6. 等 1–2 分鐘，打開 `https://2007-sunny.github.io/applied-mathematics-homework/hw4_chX/page1.html` 確認正常。
7. Google Sites：新增頁面 → 兩個文字框貼 AI 討論和 Vibe Code 連結 → 插入「嵌入」→「依網址」貼上上一步的網址 → 調整視窗大小 → 重新發布。
