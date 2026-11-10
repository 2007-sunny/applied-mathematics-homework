# 第二頁 vibe coding prompt（5.3–5.7：d/dx 的結構）

把下面整段貼給 AI（Claude / Gemini / ChatGPT）。

---

請幫我做一個互動式網頁，主題是 Arfken 第 7 版 5.3–5.7（Operators、Self-Adjoint Operators、Unitary Operators、Transformations of Operators、Invariant Subspaces）。

Prompt 規範：
- 符合 RWD 規範的互動式網頁，繁體中文與英文雙語，有按鈕切換中英文。
- 使用者可以輸入數字或用拉桿改變題目中的參數。
- 作圖顯示題目所要呈現的樣貌。
- 須提供 HTML 檔下載。
- 請注意符號與中文字型呈現的問題（數學符號用 Unicode，不依賴外部字型）。
- 網頁開頭顯示題目，並附上物理原理解析。

---- 以下依需求 ----

題目主軸：「拆解 operator D = d/dx 的結構」。空間固定為週期 2π 的 V = span{cos kx, sin kx}，k = 1…N（N 用拉桿選 1–3），內積 ⟨f,g⟩ = ∫₀^{2π} f* g dx。函數 f = Σ (a_k cos kx + b_k sin kx)，係數 a_k、b_k 用拉桿調。

模組 1：同一個 operator，兩組基底
- 實數正交歸一基底 {cos kx/√π, sin kx/√π} 下，D 的矩陣是 2×2 區塊 [[0, k], [−k, 0]] 組成的區塊對角矩陣（反對稱 → D† = −D，anti-Hermitian）。
- 有切換鈕顯示 iD 的矩陣，說明 iD 是 Hermitian。
- 複數基底 {e^{±ikx}/√(2π)}：顯示轉換矩陣 U（每個區塊 (1/√2)[[1,1],[i,−i]]），數值驗證 U†U = I，並數值算出 U†DU，顯示它是對角矩陣 diag(ik, −ik)。
- 並排列出兩組基底下的不變量：本徵值、trace、det，確認相同。
- 顯示 f 在兩組基底下的係數向量，以及兩邊算出的 ‖f‖² 相同（unitary 保內積）。

模組 2：平移算符 e^{aD}
- 拉桿調平移量 a（0 到 2π），加一個播放動畫按鈕；圖上疊畫 f(x) 與 f(x+a)。
- 顯示 e^{aD} 在實數基底下的矩陣：每個區塊是旋轉矩陣 [[cos ka, sin ka], [−sin ka, cos ka]]；在複數基底下是 diag(e^{ika}, e^{−ika})。
- 每個 k 畫一個小圖：點 (a_k, b_k) 隨 a 在圓上轉動，展示每個 {cos kx, sin kx} 是不變子空間（invariant subspace），各區塊不互相混合；即時顯示每個區塊的範數與總 ‖f‖² 不變。
- 拉桿調 Taylor 項數 M，畫出 Σ_{n≤M} aⁿDⁿf/n!，展示它收斂到 f(x+a)，說明 e^{aD} 就是 Taylor 展開。

物理原理解析要寫到：linear operator 的矩陣表示 A_mn = ⟨φ_m, Aφ_n⟩、adjoint 的定義與分部積分的邊界項（為什麼需要週期邊界條件）、self-adjoint 與 unitary、similarity transformation A' = U⁻¹AU 與不變量、invariant subspace、iD 對應動量（p = −iħ d/dx），e^{aD} 對應平移，類比 e^{−iHt/ħ}。
