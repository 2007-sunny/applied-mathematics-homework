# vibe coding prompt 範本

複製下面整段，改「以下依需求」之後的部分，貼給 AI（Claude / Gemini / ChatGPT）。

---

請幫我做一個互動式網頁，主題是 Arfken 第 7 版 X.X–X.X（節名）。

Prompt 規範：
- 符合 RWD 規範的互動式網頁，繁體中文與英文雙語，有按鈕切換中英文。
- 使用者可以輸入數字或用拉桿改變題目中的參數。
- 作圖顯示題目所要呈現的樣貌。
- 須提供 HTML 檔下載。
- 請注意符號與中文字型呈現的問題。
- 網頁開頭顯示題目，並附上物理原理解析。

技術要求（之前踩過的坑）：
- 公式用 KaTeX（從 cdnjs 載入 0.16.9 版）的 auto-render，行內用 \( \)、獨立用 \[ \]。切換語言或數值更新後，要重新呼叫 renderMathInElement（用 MutationObserver + setTimeout，不要用 requestAnimationFrame）。
- canvas 的原始高度存在 data 屬性，不要用 canvas.height 記，否則高解析度螢幕上拉滑桿圖會越來越高。
- .katex 加 position:relative，長公式放在可水平捲動的框內，避免整頁出現水平捲軸。
- 畫圖不要用外部圖表套件，直接用 canvas。

---- 以下依需求 ----

題目主軸：（一句話說清楚這頁要傳達什麼）

模組 1：（互動內容、拉桿、圖）

模組 2：（互動內容、拉桿、圖）

物理原理解析要寫到：（列出要點）
