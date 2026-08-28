# Figure 3. Cumulative alerted counties versus observed intensity-3 footprint

- **Image:** `fig03.png`
- **Section:** 4
- **Official caption:** Cumulative number of alerted counties for the three channels compared with the observed cumulative count of counties first exceeding intensity 3 (per-second intensity data). All channels reach their final coverage at 13.7 s, whereas the observed footprint grows until about 65 s. The first county exceeded intensity 3 at about 4 s, before any alert was issued.

---

## English

### What is drawn

A step plot, 0–120 s after origin, of cumulative counties/cities. Four series:

| Series | Style (on the PNG) | Value at first dispatch |
| --- | --- | ---: |
| PWS (cell broadcast) | solid green | **17** |
| School (predicted intensity ≥ 3) | dashed blue | **12** |
| Television (CAP) | dotted red | **11** |
| Observed (max intensity ≥ 3) | dash-dot grey | rises later to **15** |

All three alert series jump in the **same second at 13.67 s** and then stay flat (PWS and TV issue one message; school coverage here is counted at predicted intensity ≥ 3 on the first XML). The grey observed curve starts near 4 s (about 3 counties already at intensity 3 when the alert fires), climbs in steps as waves cross the island, and plateaus at 15 near 65 s.

### How to read it

The horizontal gap from the 13.7 s jump to each later grey step is **county-scale lead time**. Grey steps *before* 13.7 s are blind-zone counties. PWS finishing at 17 versus observed 15 is **over-coverage**. TV (11) and school (12) sit *below* 15 on the first message: those channels were slightly under-inclusive at the intensity-3 county count, while PWS was over-inclusive.

Because the three channels leave the system together, the 13.67 s delay is **source-estimation time**, not publication lag.

### Scientific meaning

Timeliness is good for most of the island (observed intensity 3 keeps growing until ~65 s). Inclusiveness of PWS is conservative. Combined with Fig. 6: the first public product is also the **least accurate** intensity map, and PWS/TV never revise it. The two extra PWS counties are the spatial cost of disseminating \(M_{Pd}\) 6.6.

### Common misreading

Do not read “school 12 < observed 15” as a missed warning on PWS. Different channels have different intensity thresholds (Table 1). The operational claim in the Abstract is about PWS: 17 versus 15.

---

## 中文

### 圖面內容

發震後 0–120 秒的累積縣市數階梯圖。四條線：

| 序列 | 圖上樣式 | 首發當下的縣市數 |
| --- | --- | ---: |
| PWS 細胞廣播 | 綠實線 | **17** |
| 學校（預測震度 ≥ 3） | 藍虛線 | **12** |
| 電視（CAP） | 紅點線 | **11** |
| 實測最大震度 ≥ 3 | 灰點虛線 | 後來升到 **15** |

三條警報線都在 **13.67 秒同一秒**跳起後持平（PWS／電視每事件一則；此圖學校以首則 XML 預測震度 ≥ 3 計）。灰色實測線約 4 秒就出現（警報發出時已約 3 縣市達震度 3），隨波前過島階梯上升，約 65 秒停在 15。

### 如何判讀

從 13.7 秒跳起到灰色後續階梯的水平距離，是縣市尺度的領先時間。13.7 秒*之前*的灰色階梯是盲區縣市。PWS 停在 17、實測 15，是**多覆蓋**。電視 11、學校 12 在首報低於 15：這兩通道在震度 3 縣市數上略不足；PWS 則略多。

三通道同時離開系統，所以 13.67 秒全是**震源估算時間**，不是發佈延遲。

### 科學意義

全島多數地區預警及時（實測震度 3 一直長到約 65 秒）。PWS 空間上偏保守。搭配圖 6：公眾第一則也是**最不准**的震度圖，且 PWS／電視不再改。多出來的兩個 PWS 縣市，就是對外發布 \(M_{Pd}\) 6.6 的空間代價。

### 容易讀錯的地方

不要把「學校 12 < 實測 15」讀成 PWS 漏報。三通道門檻不同（表 1）。摘要裡的作業結論指的是 PWS：17 對 15。
