## 基本介紹

- **Nitro** 是 Nuxt 3 的伺服器引擎，負責處理 **Server API、Middleware、部署**。
- [Nitro 官方文件](https://nitro.build/)

## 目錄結構

- `server/api/` → 建立 API 路由（自動加上 `/api` 前綴）
- `server/routes/` → 自訂伺服器路由（沒有 `/api` 前綴）
- `server/middleware/` → 請求攔截與前處理
- `server/utils/` → 共用工具函式
- `server/plugins/` → Nitro 插件（如註冊 hooks、事件處理）