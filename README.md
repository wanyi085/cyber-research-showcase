# Cyber Research Showcase 🔍

本專案為大專生研究計畫與專題實作之整合成果，聚焦於**網路封包指紋分析與攻擊來源識別**，涵蓋封包特徵萃取、蜜罐誘捕、指紋比對驗證與異常聚類分析。

本系統目標為開發一套具備「即時監控」、「可疑來源警示」、「攻擊者行為輪廓分析」的資安輔助工具。

---

## 📁 專案模組 Modules

| 模組名稱 | 功能簡述 |
|----------|-----------|
| `S2PF-sniffer/` | 基於 libpcap 實作，擷取並比對來源 IP 封包指紋，驗證 Spoof 行為並產生警示 |
| `honeypot-analysis/` | 整合 Cowrie 蜜罐日誌，萃取高風險 IP，並交叉比對 S2PF 指紋紀錄 |
| `rabin-kmeans/` | 使用 Rabin Fingerprint 對封包滑動視窗特徵建模，搭配 K-means 聚類進行攻擊行為分析 |

---

## 🧠 研究亮點

- 🔐 **S2PF（Source-to-Path Fingerprinting）驗證機制**  
  建立來源 IP 與其特徵路徑之對應指紋表，判別來源是否為假冒。

- 🐍 **Cowrie 蜜罐整合**  
  捕捉攻擊者行為與來源 IP，並與指紋比對進行異常偵測。

- ⚙️ **Rabin fingerprint + k-means 聚類**  
  利用滑動視窗方式提取封包指紋，將相似攻擊模式進行分群，形成攻擊簽章樣本。

---

## 📂 資料結構說明

cyber-research-showcase/
├── S2PF-sniffer/ # 封包擷取與指紋比對主程式
├── honeypot-analysis/ # Cowrie 蜜罐日誌整合與 IP 分析模組
├── rabin-kmeans/ # 特徵指紋生成與攻擊分群分析
└── report/ # 專題報告、成果簡報

---

## 🚀 如何使用

以下為 `S2PF-sniffer` 執行範例：

```bash
sudo ./ip_sniffer --learn        # 建立來源 IP 對應指紋表
sudo ./ip_sniffer --watch        # 比對封包指紋並產生可疑紀錄
