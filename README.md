# ID Consultant Simulator | 感染科照會模擬系統

一個 day-based 的感染症臨床決策訓練遊戲：玩家在 30 天時限內管理 4 張病床的感染症專責病房，逐一接手案例並做出診斷、抗生素選擇、source control、出院銜接等決策，目標是累計損益最大化 + 獲得最高的案例評分（系統依據決策的適切程度給分）。

**目標族群：** 感染科住院醫師（R1–R3）/ 內科住院醫師 / 對 ID 有興趣的醫師

---

## ⚠️ 重要聲明

> **本工具為教育模擬，非臨床決策參考。**
> 遊戲內的 case scenario、藥物劑量、診斷與治療建議皆為**教學設計**，並非真實臨床指引。所有臨床決策請依據病人實際狀況、最新指引與臨床判斷，並諮詢相關專科醫師。
> 本工具不可、也不應被用於指導真實病人的醫療決策。

---

## 目前已收錄案例（5 則）

| Case | 主題 | 核心教學 |
|---|---|---|
| 01 | GBS 菌血症（糖尿病足潰瘍）| Gram stain 判讀、De-escalation、TTE workup、OPAT |
| 02 | NHAP（MRSA 肺炎 + CRKP ASB）| Empiric、ASB vs infection、FilmArray、Foley source control |
| 03 | Emphysematous Pyelonephritis | ESBL E. coli sepsis、PCN vs nephrectomy、antibiotics ≠ source control |
| 04 | Post-influenza MSSA Pneumonia | CAP empiric、流感快篩限制、FilmArray、診斷延遲的代價（HFNC → VV-ECMO）|
| 05 | MRSA Vertebral Spondylodiskitis | MRSA UTI 的警示意義、hematogenous spreading、MRI / Gallium scan、嚴格臥床 + 背架的角色 |

---

## 遊戲玩法

### 基本流程
1. 開始時 4 張床位同時入住 4 個案例
2. 每張床位 Day 0 都需要：選擇 empiric 抗生素 +/- 診斷工具
3. 點「推進到 Day N+1」讓所有床位同步推進一天
4. 各案例會在特定天數觸發決策點（如 Day 1 培養初步報告、Day 3 最終藥敏 + de-escalation）
5. 病人出院 → 床位釋出 → 隊列下一個案例入住
6. 30 天時限到，所有未完成案例強制結算

### 結局類別
- **順利出院** / **治療完成（有併發症）**
- **ICU 路徑** / **VV-ECMO + 機械通氣後出院**
- **病人死亡**
- **病人轉院**因治療不如預期、無進展可能觸發
- **療程未完成**（30 天時限到但未完成治療，按住院天數比例給付，不予評分）

### 評分與損益
- 每個案例從 100 分起算，最佳決策加分、不佳決策減分、副作用扣分、結局調整
- 損益 = 個案定額給付（系統設定） + 特殊處置補助 - 藥費 - 床費 - 手術費等
- 累計評分 + 累計損益在側邊欄即時顯示

---

## 技術架構

- **純 HTML + JavaScript**，單一 .html 檔案，**無後端、無依賴**
- localStorage 自動存檔（單槽、防 save-scumming）
- 響應式設計（桌面 sidebar + 手機 Tab 切換）
- 支援 Chrome / Safari / Firefox / Edge

---

## 使用方式

### 線上版（推薦）
👉 **https://gj-chen-id.github.io/id-consultant-serious-game/**

### 離線單機版
1. 下載 `index.html`
2. 用瀏覽器打開（雙擊即可，無需安裝）
3. 進度儲存於瀏覽器 localStorage，**清除 cookies/site data 會遺失進度**

---

## 回饋與建議

試用後若有任何 bug 回報、案例建議、教學重點補充，歡迎聯繫：

📧 [https://docs.google.com/forms/d/e/1FAIpQLSflcJkts_9bID7xqmw2wyeEVl_MnE5G7PY1JwmLukyKq-Rdag/viewform?usp=publish-editor]

特別歡迎以下類型的回饋：
- 臨床決策邏輯不合理之處
- 評分加權建議
- 想加入的新案例 idea（症狀 → 診斷 → 治療思路）
- UI / 操作上的痛點

---

## 版本

**v2 — 2026-06-05**

主要架構：30 天 / 4 床、5 case pool、響應式 UI、自動存檔。

開發歷程詳見 `game-design-notes.md`（內部設計筆記）。

---

## 作者

陳冠州（Guan-Jhou CHEN）
- 國立台灣大學醫學院 內科 專案助理教授
- 敏盛綜合醫院 感染科暨感染管制室 主任

---

## License

教學使用免費分享。請保留作者資訊與免責聲明。商業使用或大規模散布前請先聯繫作者。
