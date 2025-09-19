
- [官網](https://nuxt.com/modules/pinia-plugin-persistedstate)
- [文檔](https://prazdevs.github.io/pinia-plugin-persistedstate/zh/frameworks/nuxt.html)

# 安裝

```bash
npm i pinia-plugin-persistedstate
```

在 `nuxt.config.ts` 設定模組：

```ts
export default defineNuxtConfig({
  modules: [
    '@pinia/nuxt',
    'pinia-plugin-persistedstate/nuxt' 
  ]
})
```

如果設定完重整會報錯就重啟專案看看