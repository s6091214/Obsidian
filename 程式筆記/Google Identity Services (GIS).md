## 基本介紹

- **是 Google 提供的 **新一代登入解決方案**，取代舊版 **Google Sign-In (gapi)**。
- [官方文件](https://developers.google.com/identity/gsi/web/guides/overview)
    
- 支援：
    - **Sign in with Google 按鈕**
    - **One Tap Login**（頁面右上角彈出提示）
    - **自動登入**（同裝置同瀏覽器可自動帶入憑證）
        
- 核心概念：
    - 登入後回傳一個 **Credential (JWT Token / id_token)**
    - 前端可直接解析基本資訊，或送到後端驗證