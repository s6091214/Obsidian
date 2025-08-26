## 1. 什麼是 DNS

- DNS 是「域名系統」，負責把 **好記的域名**（例如 `example.com`）轉換成 **IP 位址**（例如 `172.67.169.194`），讓電腦能互相找到對方。
    
- 簡單比喻：域名像你的「名字」，IP 像你的「地址」，DNS 就是查地址的電話簿。

## 2. DNS 基本紀錄種類

| 紀錄類型  | 說明      | 範例                                        |
| ----- | ------- | ----------------------------------------- |
| A     | IPv4 地址 | `example.com → 172.67.169.194`            |
| AAAA  | IPv6 地址 | `example.com → 2606:4700:3030::6815:1bd6` |
| CNAME | 別名      | `www.example.com → example.com`           |
| NS    | 指定域名伺服器 | `example.com → ns1.test.com`              |
| MX    | 郵件伺服器   | `example.com → mail.example.com`          |
| TXT   | 文本紀錄    | SPF、驗證紀錄                                  |
## 3. 常用 DNS 操作指令（Windows 範例）

```
# 查詢域名解析結果
nslookup example.com

# 指定 DNS 查詢
nslookup example.com 8.8.8.8

# 查詢 MX 郵件紀錄
nslookup -type=MX example.com
```
## 4. DNS 小技巧

- **檢查 [[CDN]] 生效**：`nslookup yourdomain.com`，看解析到的 IP 是否為 [[CDN]] 節點。
    
- **快取問題**：DNS 有 TTL（快取時間），修改紀錄後可能需要等幾分鐘到 24 小時生效。
    
- **多名稱伺服器**：最好至少設定兩個 NS，提高穩定性。
    