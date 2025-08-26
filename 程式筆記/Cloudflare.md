## 基本介紹

- **Cloudflare** 是 [[CDN]] + DDoS 防護 + [[DNS]] + 反向代理服務
    
- **常見用途**：
    
    - 加速網站存取
        
    - 防禦 DDoS 攻擊
        
    - [[DNS]] 解析
        

## 主要功能

- **[[DNS]]**：快速全球解析
    
- **[[CDN]]**：靜態資源快取，加速網站
    
- **SSL/TLS**：免費憑證，支援 Flexible / Full / Strict 模式
    
- **Firewall Rules**：自訂防火牆規則
    
- **Workers**：邊緣運算 (serverless)
    
- **Zero Trust**：存取控制與安全代理
    

## [[DNS]] 設置

### 新增 [[DNS]] 記錄

1. 登入 Cloudflare，選擇你的網站 → 進入 **[[DNS]]** 頁面
    
2. 點擊 **新增記錄**
    
3. 選擇記錄類型（A、CNAME、MX、TXT…）
    
4. 填入名稱、值（IP 或目標域名）
    
5. 選擇 **Proxy 狀態**（橘色或灰色雲朵）
    
6. 點擊 **保存**

### Proxy 狀態說明

- 🟠 **橘色雲朵**：流量經過 Cloudflare Proxy
    
    - [[CDN]]、SSL、Firewall 功能啟用
        
- ⚪ **灰色雲朵**：僅做 [[DNS]] 解析
    
    - 流量直接到原伺服器，不經過 Cloudflare
        

### 小技巧

- 如果要使用 [[CDN]] + SSL + 防火牆功能，建議使用橘色雲朵
    
- 某些服務（如郵件伺服器 MX 記錄）建議用灰色雲朵，避免流量被代理