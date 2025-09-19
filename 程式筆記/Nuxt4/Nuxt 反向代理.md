#### `nuxt.config.ts` 設定範例

```ts
import { defineNuxtConfig } from 'nuxt'

export default defineNuxtConfig({
  vite: {
    server: {
      proxy: {
        // 將 /api/carts 代理到遠端 /carts
        '/api/carts': {
          target: 'https://example.tw',
          changeOrigin: true,
          rewrite: path => path.replace(/^\/api\/carts/, '/carts'),
          secure: false,
        },
        // 可以新增其他代理路徑
        '/api/another': {
          target: 'https://example.com',
          changeOrigin: true,
          rewrite: path => path.replace(/^\/api/another/, '/another'),
          secure: false,
        },
      },
    },
  },
})

```

### 說明

- **`/api/carts`**：前端本地呼叫路徑
- **`target`**：實際遠端 API
- **`rewrite`**：把本地路徑替換成遠端路徑
- **`changeOrigin: true`**：修改 Host header
- **`secure: false`**：用於自簽章或開發環境

#### 前端呼叫範例

```ts

const res = await $fetch('/api/carts/test', {
  method: 'POST',
})

console.log(res)

```