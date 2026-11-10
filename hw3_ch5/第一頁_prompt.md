# 第一頁 vibe coding prompt（5.1–5.2：空間 = 區間 + 權重）

把下面整段貼給 AI（Claude / Gemini / ChatGPT）。

---

請幫我做一個互動式網頁，主題是 Arfken 第 7 版 5.1–5.2（Vectors in Function Spaces、Gram-Schmidt Orthogonalization）。

Prompt 規範：
- 符合 RWD 規範的互動式網頁，繁體中文與英文雙語，有按鈕切換中英文。
- 使用者可以輸入數字或用拉桿改變題目中的參數。
- 作圖顯示題目所要呈現的樣貌。
- 須提供 HTML 檔下載。
- 請注意符號與中文字型呈現的問題（數學符號用 Unicode，不依賴外部字型）。
- 網頁開頭顯示題目，並附上物理原理解析。

---- 以下依需求 ----

題目主軸：「函數空間由『區間 + 權重』決定」。同樣的 1, x, x², …，換了內積 ⟨f,g⟩ = ∫ w(x) f(x) g(x) dx，Gram-Schmidt 就生出不同的正交多項式。

模組 1：同樣的 1, x, x²，不同的內積
- 下拉選單選空間：[−1,1], w=1（Legendre）；[0,∞), w=e^{−x}（Laguerre）；(−∞,∞), w=e^{−x²}（Hermite）。
- 拉桿選最高階數 n（0–6），數值積分做 Gram-Schmidt，畫出 φ₀…φₙ。
- 拉桿選「第 k 步」，畫出 xᵏ、它在前面基底上的投影、以及扣掉投影後的剩餘部分，讓人看到 Gram-Schmidt 每一步在做什麼。
- 顯示 Gram 矩陣 ⟨φᵢ, φⱼ⟩，確認是單位矩陣。
- Legendre 選項多一個「球座標視角」：說明 x = cosθ、dx = −sinθ dθ，所以 w=1 就是球面上的 Jacobian sinθ；用極座標圖畫 P_l(cosθ)（正負用不同顏色）。

模組 2：Completeness 的圖像
- 用 Legendre 展開函數 f(x)，拉桿調項數 N（0–40）。
- 可選函數：方波 sgn(x)、|x|、eˣ、有限偶極在單位球面上的電位 V(θ) = 1/√(1 − d·cosθ + d²/4) − 1/√(1 + d·cosθ + d²/4)（拉桿調 d，0 < d < 2）。
- 圖一：f 與部分和 f_N 疊圖。圖二：係數 |c_l| 長條圖（偶極情況應該只有奇數 l）。圖三：誤差 ‖f − f_N‖² 隨 N 下降（對數軸），並顯示 Parseval：Σ 2|c_l|²/(2l+1) → ‖f‖²。

物理原理解析要寫到：內積三要素（區間、權重、共軛）、正交與歸一、Gram-Schmidt 公式、completeness 與 Parseval、權重就是座標的 Jacobian、偶極電位為何只剩奇數 l（標註「此為 5.2 結果的應用，生成函數見 Legendre 章」）。
