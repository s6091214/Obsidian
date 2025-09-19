## 基本介紹

- Google OAuth 是 Google 提供的 **身份驗證與授權** 機制。
- 常用於讓使用者透過 Google 帳號登入應用程式。

# 建立 OAuth 憑證

- 前往 [Google Cloud Console](https://console.cloud.google.com/)
    
- 建立專案
- 啟用 **OAuth 同意畫面**
- 建立 **OAuth 2.0 Client ID**
- 設定已授權來源

```
http://localhost
http://localhost:3000
```

設定 redirect URI（如果需要 server 驗證流程）：

```
http://localhost:5173/callback
```