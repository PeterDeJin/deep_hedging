# Deep Hedging — 深度避險

以神經網路 (deep hedging) 對選擇權做動態避險的專案。**完整成果**——含 CVaR／Entropic 風險測度、無／美國／台灣交易成本比較、AAPL／AMZN 歷史資料實驗，以及與 Black-Scholes delta hedging 的對照——整理於報告 PDF、結果圖與 HackMD；**本 repo 提交的 notebook** 實作其中核心的合成路徑深度避險。

## 結構
```text
deep_hedging.ipynb   核心程式（合成 GBM 路徑深度避險）
figures/             各情境結果圖（共 42 張）
docs/                完整報告（PDF／Word）
```

## 內容
| 檔案／資料夾 | 說明 |
|------|------|
| `deep_hedging.ipynb` | 核心程式：Keras 神經網路，在合成 GBM 資產路徑（N=30／60）上，以效用函數 (log／power utility) 為損失訓練避險策略 |
| `figures/` | 各情境結果圖：PnL、CVaR／Entropic 訓練曲線、delta hedging 比較、無/美國/台灣成本、AAPL／AMZN、避險權重等 |
| `docs/` | 專案完整報告：`deep_hedging_with_cost_model_final.pdf`（CVaR／Entropic、交易成本模型、AAPL／AMZN 實證）與 Word 版 |

> 註：CVaR／Entropic 風險測度、美/台交易成本與 AAPL／AMZN 實證屬報告與結果圖的範圍；提交的 `deep_hedging.ipynb` 為合成路徑的核心實作。

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
