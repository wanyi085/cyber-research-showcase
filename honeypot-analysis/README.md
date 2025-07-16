#### `honeypot-analysis/README.md
```markdown
# Cowrie 蜜罐分析模組
利用Docker+Macvlan對路徑指紋模組所整理出來的名單與蜜罐進行整合。
對可疑 IP 來源紀錄進行分析，並擷取各項行為做Rabin FingerPrints，取得各項行為的指紋。
接著做K-means分群，將相似指紋放在同一cluster，以便後續分析。

- 儲存 cowrie.json
- 整合 k-means 後分類群組
- 對封包異常紀錄 log

## Log 範例：
2025-07-16T02:37:12.245861Z [HoneyPotSSHTransport,9,192.168.137.135] CMD: ls
2025-07-16T02:37:12.246343Z [HoneyPotSSHTransport,9,192.168.137.135] Command found: ls 
2025-07-16T02:37:12.246593Z [HoneyPotSSHTransport,9,192.168.137.135] CMD: pwd
2025-07-16T02:37:12.247041Z [HoneyPotSSHTransport,9,192.168.137.135] Command found: pwd 
2025-07-16T02:37:12.247368Z [HoneyPotSSHTransport,9,192.168.137.135] CMD: whoami
2025-07-16T02:37:12.247798Z [HoneyPotSSHTransport,9,192.168.137.135] Command found: whoami 
2025-07-16T02:37:12.248128Z [HoneyPotSSHTransport,9,192.168.137.135] CMD: uname -a
2025-07-16T02:37:12.248457Z [HoneyPotSSHTransport,9,192.168.137.135] Command found: uname -a
2025-07-16T02:37:12.248770Z [HoneyPotSSHTransport,9,192.168.137.135] CMD: exit
2025-07-16T02:37:12.249113Z [HoneyPotSSHTransport,9,192.168.137.135] Command found: exit
