# Figure 11. Error budget of the first alert

- **Image:** `fig11.png`
- **Section:** 5
- **Official caption:** Error budget of the first alert. The +0.42 term is independent of station geometry; the +0.28 term is the azimuthal-sampling penalty, quantitatively explained by the radiation pattern (+0.29 predicted).

---

## English

### What the figure shows

A stacked (or sequential) bar identity:

\[
\underbrace{5.85}_{\text{analyst }M_L}
+\underbrace{0.42}_{\text{\(Pd\) relation, any geometry}}
+\underbrace{0.28}_{\text{one-sided azimuthal sampling}}
= \underbrace{6.55}_{\text{first Geiger solution (disseminated as }M\text{ 6.6)}}
\]

Grey: truth 5.85. Orange: +0.42 that **remains** when a well-located Geiger stream has 32 magnitude stations and ~100° gap (converged mean ~6.30). Red: +0.28 from using three stations on the P-lobe at first alert (radiation predicts +0.29). Blue: 6.55 first report.

### How to read it

Do not treat 6.6 − 5.85 = 0.75 as one blob. The +0.42 is **not** fixed by waiting or by filling the azimuthal gap; only **offshore-path recalibration** removes it (Yilan well-located bias +0.45 in Fig. 12). The +0.28 **is** reduced by requiring more magnitude stations in more than one azimuthal sector.

### Scientific meaning

This is the paper’s accounting identity. It tells operators which error is software/gates and which is calibration. Network expansion cannot eat the +0.42 for this path class.

---

## 中文

### 圖面內容

首報規模的加總恆等式：

\[
5.85\ (\text{分析師 }M_L)\ +\ 0.42\ (Pd\text{ 關係，與幾何無關})\ +\ 0.28\ (\text{單側方位取樣})\ =\ 6.55\ (\text{Geiger 首解，對外 }M\ 6.6)
\]

灰：真值 5.85。橙：即使 Geiger 已用 32 個規模站、缺口約 100°，仍留下的 +0.42（收斂約 6.30）。紅：首報三站落在 P 瓣的 +0.28（輻射預測 +0.29）。藍：6.55。

### 如何判讀

不要把 6.6−5.85=0.75 當成單一誤差。+0.42 **不是**多等幾報或補缺口就能消；要靠**外海路徑重新校正**（圖 12 宜蘭定位好的解仍 +0.45）。+0.28 可以用「更多、更分散的規模站」壓下去。

### 科學意義

這是論文的帳本：哪一塊靠閘門／軟體，哪一塊靠校正。加密測網吃不掉這條路徑的 +0.42。
