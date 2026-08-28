# Figure 12. Cross-event comparison (offshore vs near-coast)

- **Image:** `fig12.png`
- **Section:** 6
- **Official caption:** Cross-event comparison. (a) Magnitude bias of well-located solutions versus the distance to the nearest station. (b) First internal solution and first public alert latency. (c) Correlation between epicentral error and reported magnitude. (d) Magnitude bias versus latency for well-located solutions only.

---

## English

### What is drawn

Four events, identical code, each event’s own analyst P-file as reference. PNG colours: Taitung 2026 offshore \(M_L\) 5.85 (red); Yilan 2025 deep offshore \(M_L\) 7.01 (orange); Hualien 2026a near-coast \(M_L\) 5.74 (blue); Hualien 2026b inland \(M_L\) 5.01 (green).

**(a)** Well-located \(\Delta M = M_{Pd}-M_L\) vs distance to nearest station. Green shading 0–10 km = source inside/at the network; red shading >10 km = outside. Hualien pair at ~5 km: **−0.08 ± 0.17** and **−0.07 ± 0.16**. Taitung / Yilan at 14.1 / 15.8 km: **+0.38 ± 0.17** and **+0.45 ± 0.14**.

**(b)** Grouped bars: grey = first internal solution, blue = first public alert. Offshore: 12.5 / 13.7 s (Taitung) and 14.1 / 13.8 s (Yilan). Near-coast: ~8.0 s internal, **8.3 s** public. Cost: **4–6 s**. (Yilan public 13.8 s can precede its 14.1 s internal first-of-six-streams timestamp depending on which stream published.)

**(c)** Correlation \(r\)(epicentral error, \(M_{Pd}\)). Only offshore is **negative**: Taitung **−0.74**, Yilan **−0.55**. Hualien: **+0.23** and **+0.46**. Negative \(r\) is the signature of inland-directed mislocation lowering \(M_{Pd}\) (Fig. 8).

**(d)** Well-located \(\Delta M\) vs latency (median across streams). Offshore curves converge to a **positive plateau** (~+0.4 to +0.5) after ~25 s. Near-coast curves start below zero and rise toward the zero line.

### How to read it

Four events are a **case-controlled contrast**, not a population statistic. The discriminator in (a) is **inside vs outside the network** (nearest-station distance), not magnitude or depth: Yilan is larger and much deeper (67.7 km) and still overestimates with the same sign. Sign and latency generalise; the numerical −0.3 to −0.4 correction still needs a larger offshore sample (Section 6 closing paragraph).

First-report intensity within ±1 is 59.0% for Taitung versus 88.1 / 92.6 / 92.4% for the other three — consistent with Taitung’s larger first-alert overestimate, not with a generic eBEAR failure.

### Scientific meaning

The Taitung mechanism is **geometry**, not a bug unique to one earthquake. Inland QC (wait until \(M_{Pd}\) matches the catalogue; use gap) will not transfer offshore: offshore well-located solutions *remain* high. Transferable gates: path-class calibration, azimuthal spread of **magnitude** stations, and cross-stream location agreement.

### Common misreading

Do not average the four \(\Delta M\) values into one “system bias.” The design is two-versus-two. Also, Hualien 2026b’s lower “warned before intensity 3” fraction (64.2%) is not worse EEW: that smaller inland shock had a smaller intensity-3 footprint, so a larger share of stations never needed a warning.

---

## 中文

### 圖面內容

四個事件、同一套程式、各用自己的分析師 P-file。PNG 顏色：臺東 2026 外海 5.85（紅）、宜蘭 2025 深外海 7.01（橙）、花蓮 2026a 近岸 5.74（藍）、花蓮 2026b 內陸 5.01（綠）。

**(a)** 定位好的 \(\Delta M=M_{Pd}-M_L\) 對最近測站距離。綠底 0–10 km＝震源在網內／網緣；紅底 >10 km＝網外。花蓮約 5 km：**−0.08 ± 0.17**、**−0.07 ± 0.16**。臺東／宜蘭 14.1／15.8 km：**+0.38 ± 0.17**、**+0.45 ± 0.14**。

**(b)** 群組柱：灰＝首筆內部解，藍＝首報公眾警報。外海：12.5／13.7 s（臺東）、14.1／13.8 s（宜蘭）。近岸：內部約 8.0 s，公眾 **8.3 s**。外海多花 **4–6 秒**。

**(c)** 震央誤差與 \(M_{Pd}\) 的 \(r\)。只有外海是**負的**：臺東 **−0.74**、宜蘭 **−0.55**。花蓮 **+0.23**、**+0.46**。負相關就是「錯位往陸地會壓低 \(M_{Pd}\)」的簽名（圖 8）。

**(d)** 僅定位好的解，\(\Delta M\) 對延遲（各串流中位）。外海約 25 秒後收到**正的平台**（約 +0.4～+0.5）。近岸從低於 0 往零線升。

### 如何判讀

四個事件是**病例對照**，不是母體統計。(a) 的判別變數是**在網內還是網外**（最近站距離），不是規模或深度：宜蘭更大、深得多（67.7 km），高估符號仍相同。符號與延遲可以類推；−0.3～−0.4 的改正值仍要更多外海樣本。

首報震度 ±1：臺東 59.0%，其餘三事件 88.1／92.6／92.4%——對應臺東首報高估較大，不是 eBEAR 全面失效。

### 科學意義

臺東機制是**幾何**，不是單一地震的偶發 bug。內陸那套「等 \(M_{Pd}\) 對上目錄、看缺口」搬不到外海：外海定位好的解*仍然*偏高。可轉移的閘門：路徑類校正、**規模站**的方位展度、跨串流定位一致。

### 容易讀錯的地方

不要把四個 \(\Delta M\) 平均成一個「系統偏差」。設計是二對二。花蓮 2026b「震度 3 前收到警報」只有 64.2%，也不是預警變差：那個較小的內陸震，震度 3 足跡本來就小，更多測站根本不需要警報。
