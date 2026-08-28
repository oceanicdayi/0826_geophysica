# Figure 11. Error budget of the first alert

- **Image:** `fig11.png`
- **Section:** 5
- **Official caption:** Error budget of the first alert. The +0.42 term is independent of station geometry; the +0.28 term is the azimuthal-sampling penalty, quantitatively explained by the radiation pattern (+0.29 predicted).

---

## English

### What is drawn

A waterfall / sequential bar chart. Subtitle on the PNG:

\[
5.85 + 0.42\ (\text{relation bias}) + 0.28\ (\text{geometry}) = 6.55
\]

| Bar | Colour | Height | Meaning |
| --- | --- | ---: | --- |
| Analyst \(M_L\) | grey | 5.85 | catalogue truth |
| + \(Pd\) relation | orange | 6.27 | bias that remains at good geometry |
| + one-sided sampling | red | 6.55 | extra penalty of the first three stations |
| First report | blue | 6.55 | disseminated as \(M\) 6.6 |

Annotations on the PNG: the orange step “does NOT depend on geometry: even with 32 stations and gap 100° the magnitude stays here”; the red step “the radiation pattern predicts +0.29 for exactly this term.” A dashed line marks 5.85.

### How to read it

Do not treat \(6.6-5.85=0.75\) as one blob. Split it:

- **+0.42** = converged well-located Geiger \(M_{Pd}\) (~6.30) minus 5.85. Measured as the residual after a stream went from 3 to 32 magnitude stations. Independent of gap and of \(n_m\) once geometry is adequate. Recurs as +0.45 for Yilan (Fig. 12). Only **offshore-path recalibration** removes it.
- **+0.28** = first-alert 6.55 minus that converged 6.30. Predicted as \(1.16\log_{10}(1.78)=+0.29\) from the three stations’ \(|F_P|\) (Fig. 10). Reduced by requiring more magnitude stations in more than one azimuthal sector.

The public product rounded 6.55 to **6.6**.

### Scientific meaning

This is the paper’s accounting identity. It tells operators which error is software/gates (+0.28) and which is calibration (+0.42). Network expansion cannot eat the +0.42 for this path class. The identity is for the **first Geiger solution that was disseminated**, not for inland centroid solutions (those are *low* because of term 1, Fig. 8).

### Common misreading

The three terms in the Abstract are distance, radiation sampling, and path. Fig. 11 shows only the last two added onto 5.85, because the first disseminated Geiger already had a good location (4.6 km error) — term 1 is near zero *for that particular report*. Term 1 still matters for quality control: it is why badly located centroid solutions look magnitude-accurate (Fig. 8).

---

## 中文

### 圖面內容

瀑布／序列柱狀圖。PNG 副標：

\[
5.85 + 0.42\ (\text{關係偏差}) + 0.28\ (\text{幾何}) = 6.55
\]

| 柱 | 顏色 | 高度 | 意義 |
| --- | --- | ---: | --- |
| 分析師 \(M_L\) | 灰 | 5.85 | 目錄真值 |
| + \(Pd\) 關係 | 橙 | 6.27 | 幾何已經很好仍留下的偏差 |
| + 單側取樣 | 紅 | 6.55 | 首報三站的額外懲罰 |
| 首報 | 藍 | 6.55 | 對外為 \(M\) 6.6 |

圖上註記：橙色「與幾何無關：即使 32 站、缺口 100° 規模仍停在這裡」；紅色「輻射圖案正好預測這一項 +0.29」。虛線標 5.85。

### 如何判讀

不要把 \(6.6-5.85=0.75\) 當成單一誤差。拆開：

- **+0.42**＝定位好的 Geiger 收斂 \(M_{Pd}\)（約 6.30）減 5.85。以一條串流從 3 個規模站增加到 32 個之後的殘差來量。缺口與 \(n_m\) 一旦夠用就不再變。宜蘭同樣留下 +0.45（圖 12）。只有**外海路徑重新校正**能消掉。
- **+0.28**＝首報 6.55 減那個收斂 6.30。由三站 \(|F_P|\) 預測 \(1.16\log_{10}(1.78)=+0.29\)（圖 10）。要求更多、更分散的規模站可以壓這一項。

公眾產品把 6.55 四捨五入成 **6.6**。

### 科學意義

這是論文的帳本：哪一塊靠閘門／軟體（+0.28），哪一塊靠校正（+0.42）。加密測網吃不掉這條路徑的 +0.42。這個恆等式對的是**被發布的那筆 Geiger 首解**，不是內陸重心解（那些因第一項距離而*偏低*，見圖 8）。

### 容易讀錯的地方

摘要裡三項是距離、輻射取樣、路徑。圖 11 只把後兩項加在 5.85 上，因為首報那筆 Geiger 定位已經好（誤差 4.6 km）——對**該報**第一項近乎零。第一項對品管仍然重要：它解釋為什麼定位很差的重心解，規模看起來反而準（圖 8）。
