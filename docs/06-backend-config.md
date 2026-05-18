# 06 · 後臺設定

[← 回目錄](../README.md)

---

## 6.1 伺服器端計時機制

| 設定項目 | 說明 |
|---------|------|
| 計時執行端 | 伺服器端（Server-side），不依賴客戶端時間 |
| 斷線處理 | App 關閉、斷線、背景執行時計時持續不中斷 |
| 時間同步 | App 重新連線後，向伺服器查詢最新剩餘時間或已完成狀態 |
| 時區處理 | 以 UTC 為基準，前端依玩家時區顯示本地時間 |

> ⚠️ **待確認（研發）**：App 背景執行時的計時同步機制細節。

---

## 6.2 可調參數總覽

以下為後臺需支援調整的核心參數，建議透過後臺管理介面或設定檔進行管控：

### 寶箱基礎參數

| 參數名稱 | 當前值 | 說明 | 狀態 |
|---------|--------|------|------|
| `chest_visible_level` | 1 | 下 BAR 入口開始顯示的玩家等級 | ✅ 已確認 |
| `chest_unlock_level` | 30 | 解鎖遊玩的玩家等級門檻 | ✅ 已確認 |
| `chest_max_slots` | 4 | 玩家最大寶箱持有數量 | ✅ 已確認 |
| `chest_concurrent_timers` | 1 | 同時進行計時的寶箱數量上限 | ✅ 已確認 |
| `common_wait_time` | 3600 秒（1 小時） | Common 等待時間 | ✅ 已確認 |
| `rare_wait_time` | 7200 秒（2 小時） | Rare 等待時間 | ✅ 已確認 |
| `epic_wait_time` | 14400 秒（4 小時） | Epic 等待時間 | ✅ 已確認 |
| `legendary_wait_time` | 28800 秒（8 小時） | Legendary 等待時間 | ✅ 已確認 |
| `gem_min_cost` | 1 | 即時開箱最低寶石消費 | ✅ 已確認 |

### 觸發機率參數

| 參數名稱 | 當前值 | 說明 | 狀態 |
|---------|--------|------|------|
| `bet_tier_low_threshold` | TBD | 低下注區間上限 | 🔴 待確認 |
| `bet_tier_mid_threshold` | TBD | 中下注區間上限 | 🔴 待確認 |
| `prob_common_low_bet` | TBD | 低下注區間 Common 機率 | 🔴 待確認 |
| `prob_rare_low_bet` | TBD | 低下注區間 Rare 機率 | 🔴 待確認 |
| `prob_common_mid_bet` | TBD | 中下注區間 Common 機率 | 🔴 待確認 |
| `prob_rare_mid_bet` | TBD | 中下注區間 Rare 機率 | 🔴 待確認 |
| `prob_epic_mid_bet` | TBD | 中下注區間 Epic 機率 | 🔴 待確認 |
| `prob_common_high_bet` | TBD | 高下注區間 Common 機率 | 🔴 待確認 |
| `prob_rare_high_bet` | TBD | 高下注區間 Rare 機率 | 🔴 待確認 |
| `prob_epic_high_bet` | TBD | 高下注區間 Epic 機率 | 🔴 待確認 |
| `prob_legendary_high_bet` | TBD | 高下注區間 Legendary 機率 | 🔴 待確認 |

### 獎勵參數

| 參數名稱 | 當前值 | 說明 | 狀態 |
|---------|--------|------|------|
| `reward_min_common` | TBD | Common 保證最低幣值（× TB） | 🔴 待確認 |
| `reward_min_rare` | TBD | Rare 保證最低幣值（× TB） | 🔴 待確認 |
| `reward_min_epic` | TBD | Epic 保證最低幣值（× TB） | 🔴 待確認 |
| `reward_min_legendary` | TBD | Legendary 保證最低幣值（× TB） | 🔴 待確認 |
| `reward_max_multiplier` | TBD | 幣值獎勵上限倍率 | 🔴 待確認 |
| `may_win_items_common` | TBD | Common May Win 可掉落品項 | 🔴 由運營設定 |
| `may_win_prob_common` | TBD | Common May Win 掉落機率 | 🔴 由運營設定 |
| `may_win_items_rare` | TBD | Rare May Win 可掉落品項 | 🔴 由運營設定 |
| `may_win_prob_rare` | TBD | Rare May Win 掉落機率 | 🔴 由運營設定 |
| `may_win_items_epic` | TBD | Epic May Win 可掉落品項 | 🔴 由運營設定 |
| `may_win_prob_epic` | TBD | Epic May Win 掉落機率 | 🔴 由運營設定 |
| `may_win_items_legendary` | TBD | Legendary May Win 可掉落品項 | 🔴 由運營設定 |
| `may_win_prob_legendary` | TBD | Legendary May Win 掉落機率 | 🔴 由運營設定 |

### 寶石即時開箱換算

| 參數名稱 | 當前值 | 說明 | 狀態 |
|---------|--------|------|------|
| `gem_cost_formula` | TBD | 寶石費用 = f(剩餘時間) 的換算公式 | 🔴 待確認 |
| `gem_cost_per_minute` | TBD | 每分鐘對應寶石費用（若為線性公式） | 🔴 待確認 |

> ⚠️ 所有標記 🔴 的參數需由**數值企劃**確認後填入。

---

## 6.3 觸發倍率參數

| 參數名稱 | 當前值 | 說明 | 狀態 |
|---------|--------|------|------|
| `trigger_multiplier_N` | TBD | 觸發門檻倍率：單次贏分 ≥ TB × N 時發放寶箱 | 🔴 待確認 |

---

## 6.3 押注段解鎖參數

押注段與寶箱稀有度解鎖的對應關係，可由後臺隨時調整：

| 參數名稱 | 當前值 | 說明 |
|---------|--------|------|
| `unlock_tier1_bet_min` | 1 | Common 解鎖起始押注段 |
| `unlock_tier1_bet_max` | 4 | Common 獨占結束押注段 |
| `unlock_tier2_bet_min` | 5 | Rare 解鎖起始押注段 |
| `unlock_tier2_bet_max` | 11 | Rare 解鎖結束押注段 |
| `unlock_tier3_bet_min` | 12 | Epic 解鎖起始押注段 |
| `unlock_tier3_bet_max` | 17 | Epic 解鎖結束押注段 |
| `unlock_tier4_bet_min` | 18 | Legendary 解鎖起始押注段（18 段以上全解鎖） |

> 調整此參數可即時影響玩家在 ELIGIBLE FOR 面板中看到的解鎖狀態與進度條。

---



## 6.4 待確認事項彙整（依部門）

### 數值企劃

- [ ] May Win 額外獎勵的掉落機率表（各等級分別列出）
- [ ] 即時開箱所需寶石與剩餘時間的換算公式
- [ ] 幣值獎勵的上限設定
- [ ] 各等級最低幣值獎勵數值

### 產品企劃

- [ ] 寶箱獎勵是否與帳號等級或 VIP 等級連動？
- [ ] 推播通知是否為本版本 scope？

### 文案組

- [ ] 倒數完成推播通知文案（各語言版本）

### 美術

- [ ] Legendary 寶箱專屬開箱動畫規格與素材清單
- [ ] 各稀有度開箱動畫差異規格

### 研發

- [ ] 確認伺服器端計時不依賴客戶端時間
- [ ] App 背景執行時的計時同步機制

---

### 確認進度追蹤

| 部門 | 待確認項目數 | 狀態 |
|------|------------|------|
| 數值企劃 | 5 | 🔴 未開始 |
| 產品企劃 | 3 | 🔴 未開始 |
| 文案組 | 3 | 🔴 未開始 |
| 美術 | 2 | 🔴 未開始 |
| 研發 | 2 | 🔴 未開始 |

---

[← 演出動態](05-animations.md) ｜ [↑ 回目錄](../README.md)
