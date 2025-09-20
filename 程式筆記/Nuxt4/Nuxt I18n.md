## 基本介紹

- Nuxt I18n 是 Nuxt 官方維護的國際化模組。
- 基於 Vue I18n，支援多語系、自動路由前綴、Lazy Load 語言檔案。
- [文檔](https://i18n.nuxtjs.org/docs/getting-started)
- [基本設定](https://i18n.nuxtjs.org/docs/getting-started/usage)

# 快速安裝

```bash
npx nuxi@latest module add @nuxtjs/i18n
```

## 配置

- 在 **專案根目錄** 建立 `i18n/` 資料夾
- 在 `i18n/locales/` 下放各語言 JSON 檔，才會被模組讀取到

**範例：`nuxt.config.ts`**

```ts
export default defineNuxtConfig({
  modules: ['@nuxtjs/i18n'],

  i18n: {
    locales: [
      { code: 'en', iso: 'en-US', file: 'en.json', name: 'English' },
      { code: 'zh', iso: 'zh-TW', file: 'zh.json', name: '繁體中文' }
    ],
    defaultLocale: 'zh',
    langDir: 'locales/',
    strategy: 'prefix_except_default',
  }
})

```