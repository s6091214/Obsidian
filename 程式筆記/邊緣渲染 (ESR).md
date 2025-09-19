## 基本介紹

- **Edge Rendering** 是把頁面在 **CDN 邊緣節點**，執行 SSR。
    
- 這樣可以讓使用者在 **最近的節點** 拿到動態內容，減少延遲。
    
- 適合 **需要即時資料，但又要快** 的頁面，例如：
    - 個人化首頁
    - 地區性內容（台灣顯示繁中，美國顯示英文）
    - A/B 測試

目前可以利用 ESR 的平台有：

- 使用 [[git]] 整合和`nuxt build`指令進行零設定的[Cloudflare Pages](https://pages.cloudflare.com/)
- [Vercel Edge 函數](https://vercel.com/features/edge-functions)使用`nuxt build`指令和`NITRO_PRESET=vercel-edge`環境變數
- [Netlify Edge Functions](https://www.netlify.com/products/#netlify-edge-functions)使用`nuxt build`指令和`NITRO_PRESET=netlify-edge`環境變量