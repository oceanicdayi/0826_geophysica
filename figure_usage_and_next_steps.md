# 圖片使用現況與下一步 / Figure use and next steps

對照對象：稿件 `taitung_offshore_eew_manuscript.md`，倉庫根目錄 `fig01.png`–`fig12.png`（缺 `fig10.png`）。規模一律只看作業 \(M_{Pd}\)。逐張畫面說明見 [`figure_notes/`](figure_notes/README.md)。

This note records how each figure is used in the manuscript and what to do next. The paper analyses only operational \(M_{Pd}\). Panel-level reading notes are in [`figure_notes/`](figure_notes/README.md).

---

## 1. 論證怎麼用這 12 張圖 / How the 12 figures carry the argument

| 階段 | 圖 | 在論文裡的工作 |
| --- | --- | --- |
| 幾何前提 | **1** | 測網全在陸上、震源在外海：後面所有偏差都由此而來 |
| 作業表現 | **2, 3, 6, 7** | 首報夠快、空間略多報、震度無人被低估；盲區在綠島／臺東沿岸 |
| 定位與規模隨時間 | **4, 5** | Geiger 會收到外海；幾何中心可停在陸上；\(M_{Pd}\) 停在 6.1–6.4，不是 5.85 |
| 高估三項 | **8 → 9 → 10 → 11** | 距離項 → 單側取樣 → 輻射不是方向性 → 帳本 \(5.85+0.42+0.28=6.55\) |
| 是否可推廣 | **12** | 外海兩事件高估、近岸兩事件近零；外海多花 4–6 秒 |

Story order: Fig. 1 states the one-sided geometry. Figs 2–3 and 6–7 show that the first public product was timely and conservative (over-alert, not miss). Figs 4–5 show location and \(M_{Pd}\) evolving. Figs 8–11 decompose the first-alert \(M_{Pd}\) 6.6. Fig. 12 tests whether that overestimate is offshore-specific.

正文引用順序現在是 1 → 2 → 3 → 4/5/6 → 7 → 8 → 9 → 10/11 → 12，符合期刊「依出現順序編號」的要求。第 3 節不再提前引用圖 8。

---

## 2. 逐張：引用位置、支持的句子、檔案狀態

| 圖 | 檔案 | 章節 | 正文拿它證明什麼 | PNG | 建議 |
| --- | ---: | --- | --- | --- | --- |
| 1 | `fig01.png` | §1, §2 | 551 強震／228 速度站；東岸以東無站；RMT 沙灘球 182°/50°/60° | 有，與圖說相符 | 可選：不要在圖上畫對照事件（已不在圖說裡） |
| 2 | `fig02.png` | §4 | 首報 PWS 17 縣市；0 秒圓＝盲區 | 有 | 標題 M5.8 改為 \(M_L\) 5.85 |
| 3 | `fig03.png` | §4 | 13.67 s 同時發出：PWS 17、學校 12、電視 11；實測震度 3 長到 15 | 有 | 無需重畫 |
| 4 | `fig04.png` | §4 | 早期重心在陸上 35–43 km；Geiger 往黃星收斂 | 有 | **重畫**：拿掉 `Comp 192` / `f43` / `gei`，改標 geometric-centre / Geiger |
| 5 | `fig05.png` | §4 | \(M_{Pd}\) 先 6.5–6.6 後停 6.1–6.4；定位改善消不掉高估 | 有 | 同上重標圖例；參考線寫 5.85 而非 5.8 |
| 6 | `fig06.png` | §4 | 首報殘差全 ≥ 0（10.2% 正確、無人低估） | 有，但**畫面標題寫 Figure 7** | **必須改編號** |
| 7 | `fig07.png` | §4 | 22.6°N 在警報前已達強震度；北部有數十秒領先 | 有 | 警報線 14.0 s 改與正文 13.67 s 一致 |
| 8 | `fig08.png` | §5 | 同一 \(Pd\)、不同 \(R\) → 6.55 vs 5.66；\(r=-0.74\)；關係 rms 0.13 | 有 | 拿掉內部串流名 `192_f43`；標題可去掉 “inference 2” |
| 9 | `fig09.png` | §5 | 45–180° 無站；首報三站 12°；WNW &lt;60 km 中位 6.54 | 有 | 標題可去掉 “inference 1”；**缺口–定位假相關不要畫在這張**（正文已不再把那段掛在 Fig. 9） |
| 10 | **缺檔** | §5 | P 瓣上的三站；PGA 對 \(\|F_S\|\) 指數 1.13；無殘餘方向性 | **沒有 `fig10.png`** | **最高優先：補圖** |
| 11 | `fig11.png` | §5 | \(5.85+0.42+0.28=6.55\) | 有，與正文一致 | 無需重畫 |
| 12 | `fig12.png` | §6, §7 | 外海 +0.38/+0.45 vs 近岸 ~0；延遲 4–6 s；僅外海 \(r&lt;0\) | 有 | 無需重畫 |

圖 9 之後那兩句「方位缺口 \(r=0.23\)／錯位解 \(r=0.76\)」**沒有對應的圖**。這是正文論點，不是圖 9 的內容。下一步若要視覺化，應另做一張（見第 4 節），不要塞進圖 9。

---

## 3. 稿件裡已經改過的用法 / Caption and citation fixes already in the paper

這些已寫進目前分支（PR #15），不必再改文字：

1. 第 3 節改為「見第 5 節」，不再在圖 2 之前引用 Fig. 8d。
2. Fig. 9 只標在方位取樣／熱圖／殘差那幾句，不再標在缺口品管那幾句。
3. 圖 1 圖說不再暗示對照事件畫在地圖上。
4. 圖 4、5 圖說寫明：圓點＝幾何中心，三角＝Geiger。
5. 圖 5 圖說改為 \(M_{Pd}\)；深度「除短暫跳動外」落在 10/20/30 km。
6. 圖 7 圖說改為 4–13 秒達震度 4–5，與正文一致。
7. Markdown 路徑改為根目錄 `fig01.png` … `fig12.png`（不再指向不存在的 `../figures/manuscript/`）。

---

## 4. 建議下一步（請依序做）/ Recommended next steps

### 必須 / Must

1. **補上 `fig10.png`**  
   稿件第 5 節與圖說已寫死四聯圖：(a) 下半球 P 波輻射＋166 站＋首報三站；(b) \(\|F_P\|\)、\(\|F_S\|\) 對方位；(c) 距離改正 PGA 對 \(\|F_S\|\)；(d) 去掉輻射前後的方位殘差。沒有這張檔，圖 10 無法投稿。規格見 [`figure_notes/fig10.md`](figure_notes/fig10.md) 與稿件 Figure 10 圖說。

2. **重出 `fig06.png` 的編號**  
   畫面標題目前是 Figure 7，稿件是 Figure 6。投稿時會直接衝突。

### 應該 / Should（重畫現有 PNG）

3. **圖 4、5、8：拿掉內部主機／串流代碼**  
   正文已只用 geometric-centre / Geiger。PNG 上的 `Comp 192`、`f43`、`gei`、`192_f43` 與全文風格不一致，也無法從圖說解讀。

4. **統一事件標籤為 \(M_L\) 5.85**  
   圖 2、4、5、7、9、11 標題常寫 M5.8。

5. **圖 7 警報時刻**  
   圖上 PWS / 1st alert 標 14.0 s，正文是 13.67 s。改標 13.7 s 或 13.67 s。

### 可以 / Optional

6. **要不要另做一張「缺口對定位誤差」圖**  
   第 5、7 節的核心品管論點（缺口小的六筆解定位最差）目前沒有圖。若期刊要求「重要結果都要有圖」，補一張 scatter（缺口 vs 震央誤差，分定位好／不好）即可；**不要改圖 9**。

7. **圖 8、9 去掉 “inference 1/2” 標題**  
   那是分析草稿編號，讀者沒有 “inference” 清單。

8. **投稿檔案**  
   Acta Geophysica：圖與正文分開上傳、半色調 ≥ 300 dpi；圖說集中放文末。現有 PNG 可當底稿，但圖 10 仍缺。

### 不必做 / Do not

- 不要在圖或正文再引入 \(M_{tc}\) / \(M_{all}\) / \(\tau_c\)。
- 不要把圖 11 的 +0.42（路徑關係）與圖 9c 諧波振幅 +0.42 當成同一個數。
- 不要為了「圖 4 看起來都收到黃星」而改掉正文「一條重心串流最終誤差 36 km」——那條軌跡應在圖 5b 看持續高誤差；若圖 4 終點看不出來，重畫時把未收斂的重心軌跡留在陸上。

---

## 5. 檢查清單 / Checklist before submission

- [ ] 倉庫有 `fig10.png`，且與 Figure 10 圖說四聯一致  
- [ ] `fig06.png` 標題為 Figure 6  
- [ ] 圖 4、5、8 圖例無內部串流代碼  
- [ ] 所有 PNG 事件標籤為 \(M_L\) 5.85（或 Taitung 2026）  
- [ ] 圖 7 警報線與 13.67 s 一致  
- [ ] 正文仍依序引用 Fig. 1 … 12，且只討論 \(M_{Pd}\)  
- [ ] 投稿用圖與 markdown 檔名一致（`fig01.png` … `fig12.png`）
