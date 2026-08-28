# Figure 12. Cross-event comparison (offshore vs near-coast)

- **Image:** `fig12.png`
- **Section:** 6
- **Official caption:** Cross-event comparison. (a) Magnitude bias of well-located solutions versus the distance to the nearest station. (b) First internal solution and first public alert latency. (c) Correlation between epicentral error and reported magnitude. (d) Magnitude bias versus latency for well-located solutions only.

---

## English

### What the figure shows

Four events, same code, each event’s own analyst P-file as reference: Taitung 2026 offshore \(M_L\) 5.85; Yilan 2025 deep offshore \(M_L\) 7.01; Hualien 2026a near-coast \(M_L\) 5.74; Hualien 2026b inland \(M_L\) 5.01.

**(a)** Well-located \(\Delta M\) vs distance to nearest station. Inside ~5 km (Hualien): bias ≈ 0 (−0.08, −0.07). Outside ~14–16 km (Taitung, Yilan): **+0.38, +0.45**. Discriminator is **inside vs outside the network**, not event size (Yilan is larger and deeper, same sign).

**(b)** First internal solution and first public alert. Offshore: ~12.5–14.1 s internal, **~13.7 s** public. Near-coast: **~7.9–8.3 s**. Cost: **4–6 s**.

**(c)** Correlation \(r\)(epicentral error, \(M_{Pd}\)). Only offshore is **negative** (−0.74, −0.55): inland-directed mislocation lowers \(M\). Near-coast \(r\) is weakly positive.

**(d)** Well-located \(\Delta M\) vs latency. Near-coast curves **fall toward 0**. Taitung **starts high and falls to a biased plateau** (~+0.4). (Discussion: near-coast can start *below* truth and rise; Taitung starts above.)

### How to read it

Four events are a **case-controlled contrast**, not a population statistic. Sign and latency generalise; the numerical −0.3 to −0.4 correction still needs a larger offshore sample (Section 6 closing paragraph).

### Scientific meaning

The Taitung mechanism is **geometry**, not a bug unique to one earthquake or to eBEAR as a whole. Inland QC (wait until \(M\) matches catalogue; use gap) will not transfer offshore. Calibration + magnitude-station spread + cross-stream location agreement are the transferable gates.

---

## 中文

### 圖面內容

四個事件、同一套程式、各用自己的分析師 P-file：臺東 2026 外海 5.85、宜蘭 2025 深外海 7.01、花蓮 2026a 近岸 5.74、花蓮 2026b 內陸 5.01。

**(a)** 定位好的 \(\Delta M\) 對最近測站距離。約 5 km 內（花蓮）偏差≈0；約 14–16 km 外（臺東、宜蘭）**+0.38、+0.45**。關鍵是**在網內還是網外**，不是規模或深度（宜蘭更大更深，符號相同）。

**(b)** 首筆內部解與首報公眾警報。外海內部約 12.5–14.1 s、公眾 **約 13.7 s**；近岸 **約 7.9–8.3 s**。外海多花 **4–6 秒**。

**(c)** 震央誤差與 \(M_{Pd}\) 的 \(r\)。只有外海是**負的**（−0.74、−0.55）：錯位往陸地會把 \(M\) 壓低。近岸 \(r\) 弱正。

**(d)** 僅定位好的解，\(\Delta M\) 對延遲。近岸曲線**朝 0 收斂**；臺東**一開始就高，落到偏置平台**（約 +0.4）。

### 如何判讀

四個事件是**病例對照**，不是母體統計。符號與延遲可以類推；−0.3～−0.4 的改正值仍要更多外海樣本。

### 科學意義

臺東機制是**幾何**，不是單一地震或整套 eBEAR 的偶發 bug。內陸那套「等規模對上目錄、看缺口」搬不到外海。可轉移的是：路徑校正、規模站方位展度、跨串流定位一致。
