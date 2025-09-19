## 基本介紹

- Nuxt 提供多種渲染模式（[[客戶端渲染（CSR）|CSR]]、[[伺服器端渲染（SSR）|SSR]]、[[靜態網站生成（SSG）|SSG]]、[[增量靜態再生（ISR）|ISR]]），但在實際專案中，**可以同時混用**。
- **混合渲染** 指的是根據頁面或 API 的需求，決定不同的渲染策略，以達到最佳效能與使用者體驗。

## 使用情境

- **首頁**：使用 **SSR** → 兼顧 SEO 與即時資料。
- **文章頁面**：使用 **SSG 或 ISR** → 靜態生成，降低伺服器負擔。
- **管理後台**：使用 **CSR** → 資料多為登入後才取用，SEO 不重要。

## 設定方式

在 `definePageMeta` 中指定 `ssr` 與 `prerender`，或用 `nuxt.config` 全域設定。

### 頁面層級控制

```ts
<script setup>
definePageMeta({
  ssr: true, // 此頁面啟用 SSR
})
</script>
```

在 **`nuxt.config.ts`** 中使用 `routeRules` 可以針對不同路由設定不同渲染策略或功能。

```ts
export default defineNuxtConfig({
  routeRules: {
    // 首頁：在 build 時預先產生 (SSG)
    '/': { prerender: true },

    // Products 頁：按需生成，背景 revalidate，快取直到 API 變動
    '/products': { swr: true },

    // 單一 product 頁：按需生成，背景 revalidate，每小時更新
    '/products/**': { swr: 3600 },

    // Blog 列表頁：ISR，每小時更新
    '/blog': { isr: 3600 },

    // Blog 單篇文章：只生成一次，直到下次部署才更新
    '/blog/**': { isr: true },

    // Admin 後台：僅在客戶端渲染 (CSR)
    '/admin/**': { ssr: false },

    // API：自動加上 CORS headers
    '/api/**': { cors: true },

    // 舊網址導向新網址
    '/old-page': { redirect: '/new-page' }
  }
})

```

# redirect常見使用情境

**網站改版 / SEO 維護**

- 你原本有 `/old-page`，但新網站路由改成 `/new-page`。
- 為了避免舊網址進來的使用者看到 404，要自動導去新頁面。
- 同時保留 **搜尋引擎排名 (SEO)**。

**內容搬移**

- 文章從 `/blog/123` 移到 `/posts/123`。
- 就要設一個 redirect，讓舊連結仍然有效。

```ts
'/blog/**': { redirect: '/posts/**' }
```

**多語系切換**

- 如果你把 `/about` 改到 `/zh/about`，就可以自動轉去對應語系。

```ts
'/about': { redirect: '/zh/about' }
```

**舊活動頁 / 廣告連結**

- 舊的活動頁 `/summer-sale-2023`，要導到新的 `/sale`。

```ts
'/summer-sale-2023': { redirect: '/sale' }
```
