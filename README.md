# Deep Hedging — 深度避險

以神經網路 (deep hedging) 對選擇權做動態避險，並與傳統 Black-Scholes delta hedging 比較；納入 CVaR / Entropic 風險測度與交易成本模型（無成本 / 美國成本 / 台灣成本），標的含 AAPL、AMZN。

## 內容
| 檔案 | 說明 |
|------|------|
| `deep_hedging.ipynb` | 主程式：Keras 神經網路，模擬 GBM 資產路徑（N=30 期），訓練避險策略 |
| `deep_hedging_with_cost_model _final.pdf` | 專案完整報告 |
| `Deep Hedging with Transaction Cost Model.docx` | 報告（Word 版）|
| `*.png`（40+ 張）| 各情境結果圖：PnL、CVaR／Entropic 訓練曲線、delta hedging 比較、避險權重等 |

## 執行
```bash
pip install tensorflow numpy matplotlib
```

## 延伸閱讀：完整理論說明（HackMD）

本專案的理論推導與方法完整整理於 HackMD —— **Deep Hedging URP**：
<https://hackmd.io/@JYang/SJOMoqNWA/%2Fr6l2ZZouT-ivlYcLy0aeJg>

內容分為五部分：
1. **Introduction & Market Framework** — 動機與市場框架：離散時間市場設定、交易策略、自融資投組，含／不含交易成本的損益 (PnL) 定義
2. **Pricing and Hedging with Convex Risk Measures** — 以凸風險測度進行定價與避險
3. **Approximating Hedging Strategies by Deep Neural Networks** — 用深度神經網路逼近最適避險策略
4. **Numerical Experiments** — 以 Black-Scholes 模擬比較 Deep Hedging 與傳統 Delta Hedging，並分析交易成本的影響
5. **History Data experiment** — 以 AAPL、AMZN 歷史資料驗證實務表現
