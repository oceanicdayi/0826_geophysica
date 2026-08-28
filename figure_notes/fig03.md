# Figure 3. Cumulative alerted counties versus observed intensity-3 footprint

- **Image:** `fig03.png`
- **Section:** 4
- **Official caption:** Cumulative number of alerted counties for the three channels compared with the observed cumulative count of counties first exceeding intensity 3 (per-second intensity data). All channels reach their final coverage at 13.7 s, whereas the observed footprint grows until about 65 s. The first county exceeded intensity 3 at about 4 s, before any alert was issued.

---

## English

### What the figure shows

A step plot versus time after origin (0–120 s). Three alert series jump at **13.67 s**:

| Channel | Counties at first (and only simultaneous) dispatch |
| --- | --- |
| PWS (cell broadcast) | 17 |
| School (predicted intensity ≥ 3) | 12 |
| Television (CAP) | 11 |

A fourth series (observed counties with max intensity ≥ 3) rises in steps from ~4 s to ~65 s and plateaus at **15**.

### How to read it

Horizontal distance from the 13.7 s jump to each step of the grey “observed” curve is **lead time at county scale**. Early grey steps at ~4 s (before any alert) are the blind-zone counties. PWS finishing above 15 is **over-coverage**; TV and school sit below 15 on the first message (school later updates; not all shown as extra jumps if coverage is counted at predicted intensity ≥ 3 on the first XML).

The three channels leave the system in the **same second**, so the 13.67 s delay is source-estimation time, not channel lag.

### Scientific meaning

Timeliness is good for most of the island; inclusiveness of PWS is conservative. The plot also shows that **the first public product is issued once and is not revised** on PWS/TV, so the least accurate intensity map (Fig. 6, first report) is the one the public keeps.

---

## 中文

### 圖面內容

發震後累積「已警報縣市數」對時間的階梯圖。三條警報線都在 **13.67 秒** 跳起：PWS 17、學校（預測震度 ≥ 3）12、電視 11。灰色「實測最大震度 ≥ 3」的縣市數約從 4 秒爬到 65 秒，停在 **15**。

### 如何判讀

13.7 秒垂直跳起到灰色階梯的水平距離，就是該縣市尺度的領先時間。約 4 秒就出現的灰色階梯是盲區縣市（警報前已達震度 3）。PWS 高於 15 是**多覆蓋**；電視與學校首報低於 15。三通道**同一秒**發出，13.67 秒全是震源估算時間，不是通路延遲。

### 科學意義

全島多數地區預警及時；PWS 空間上偏保守。PWS／電視通常每事件只發一次，因此公眾拿到的是最不准的那張震度圖（見圖 6 首報）。
