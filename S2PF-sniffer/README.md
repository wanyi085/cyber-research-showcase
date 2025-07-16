# S2PF-sniffer

基於 libpcap 的封包擷取工具，用於學習與比對 S2PF 指紋資料。

## 功能
- `--learn` 模式：學習來源 IP 對應的封包指紋
- `--watch` 模式：偵測來源與指紋是否符合，並產生警示
- 儲存指紋為 JSON
- 支援 LFU/LRU 替換策略

## 執行方式
```bash
sudo ./ip_sniffer --learn
