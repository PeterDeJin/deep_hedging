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
