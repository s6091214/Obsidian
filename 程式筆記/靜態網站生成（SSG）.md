## 基本介紹

- **SSG (Static-Site Generation)**：在 **build 階段** 就把頁面渲染成靜態 HTML，放到伺服器或 CDN 上。
- 使用者請求時，直接回傳已經產生好的 HTML → 載入速度快。    
- 適合 **內容不常變動** 或 **可預先產生** 的網站。

## 優點

- 首次載入最快（直接回傳 HTML）
- **SEO 佳**（跟 SSR 一樣）
- 部署便宜、可用 CDN global cache

## 缺點

- 資料固定 → 更新內容需要 **重新 build**
- 不適合 **即時性高** 的應用（例如即時股價、聊天室）

## 使用情境

- 文件網站（Docs, Knowledge Base）
- 部落格
- Landing page（行銷頁面）
- 內容更新不頻繁的網站