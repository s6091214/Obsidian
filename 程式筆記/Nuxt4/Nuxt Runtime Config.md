## 基本介紹

- 公開配置和環境變量。
- [文檔](https://nuxt.com/docs/4.x/guide/going-further/runtime-config)

# 設定 (`nuxt.config.ts`)

```ts
export default defineNuxtConfig({
  runtimeConfig: {
    apiSecret: '123',
    public: {
      apiBase: '/api' 
    }
  }
})
```

# 使用

```ts
const runtimeConfig = useRuntimeConfig()

console.log(runtimeConfig.apiSecret)
console.log(runtimeConfig.public.apiBase)
```

# 搭配 .env
- 必須先設定runtimeConfig，env的設定值才能覆蓋過去。
```ts
NUXT_API_SECRET=abc
NUXT_PUBLIC_API_BASE=https://example.com
```