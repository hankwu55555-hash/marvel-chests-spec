# 🎁 Marvel Chests — 功能規格書

> **版本：** v1.0 ｜ **建立日期：** 2026-05-13 ｜ **狀態：** 草稿（待企劃確認）

Marvel Chests 是一個與老虎機轉輪綁定的寶箱獎勵系統。玩家透過轉輪觸發 Epic Win 獲得不同稀有度的寶箱，每個寶箱需等待倒數時間後才能開啟，並可使用寶石縮短等待。整體機制旨在提升每日回訪率（DAU）與付費轉換。

---

## 📂 文件目錄

| 章節 | 說明 |
|------|------|
| [01 · 寶箱等級規格](docs/01-chest-levels.md) | 4 種稀有度、等待時間、獎勵倍率 |
| [02 · 獲得機制](docs/02-acquisition.md) | 觸發條件、下注與稀有度關係 |
| [03 · 計時與開箱機制](docs/03-timer-opening.md) | 啟動規則、開箱方式、容量限制 |
| [04 · 獎勵規格](docs/04-rewards.md) | 幣值獎勵、額外獎勵（May Win） |
| [05 · 邊界情境](docs/05-edge-cases.md) | 6 個 Edge Cases 與預期行為 |
| [06 · 優化建議](docs/06-improvements.md) | 競品分析後的 4 條改進方向 |
| [07 · 待確認事項](docs/07-pending.md) | 需各部門確認的開放問題 |

---

## ⚡ 快速摘要

### 寶箱等級一覽

| 等級 | 等待時間 | 最低幣值 | 額外獎勵 |
|------|---------|---------|---------|
| 🟠 Common | 1 小時 | ≥ 0.4x TB | 寶石、拼圖碎片 |
| 🔵 Rare | 2 小時 | ≥ 1x TB | Ball Shots、拼圖碎片 |
| 🟣 Epic | 4 小時 | ≥ 2x TB | Ball Shots、拼圖碎片 |
| 🔴 Legendary | 8 小時 | ≥ 4x TB | Ball Shots、拼圖碎片 |

> TB = Total Bet（觸發 Epic Win 時的總下注額）

### 核心規則

- 同時只能啟動 **1 個**寶箱計時
- 最多持有 **4 個**寶箱（滿格不再發放）
- 可用 **寶石**即時開啟，剩餘時間越長花費越多
- **Instant Bonus** 與 **Wild Bisons** 觸發的 Epic Win 不計入

---

## 🔄 Changelog

詳見 [CHANGELOG.md](CHANGELOG.md)

---

> 本規格書依據遊戲截圖分析產出，最終規格以企劃確認版本為準。
