## 官網 / 文件
- [GitHub Repo](https://github.com/nuxt-modules/tailwindcss)
- [官方文件](https://tailwindcss.nuxtjs.org/getting-started/installation)

# 安裝

```bash
npm i -D @nuxtjs/tailwindcss
```


## 設定

在 `nuxt.config.ts` 裡加入：

```ts
export default defineNuxtConfig({
  modules: ['@nuxtjs/tailwindcss'],
})
```


## 備註

- `-D` 代表安裝為 **開發依賴**
    
- Nuxt 模組會自動幫你配置好 [[PostCSS 基本介紹與指令]]