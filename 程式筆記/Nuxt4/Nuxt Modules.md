## 基本介紹

- **Modules** 是 Nuxt 的擴充機制，可以在建置或執行階段整合功能。
    
- 與 **Plugins** 不同，Modules 可以更深度地修改 Nuxt 的設定，例如：
    
    - 新增 Vite / Webpack 設定
        
    - 自動註冊元件
        
    - 設定 Runtime Config
        
    - 自動安裝與整合外部套件
        
- 適合封裝重複性邏輯，或分享給不同專案使用。

## 官網資源

- [Modules 市集 (Nuxt 官方)](https://nuxt.com.cn/modules?category=Official)
    
- [安裝與建立模組範例](https://nuxt.com/docs/4.x/guide/concepts/modules)

## 使用方式

### 安裝現有模組

以安裝 `@nuxtjs/tailwindcss` 為例：

```bash
npm install -D @nuxtjs/tailwindcss
```

然後在 `nuxt.config.ts` 中加入：

```ts
export default defineNuxtConfig({
  modules: [
    '@nuxtjs/tailwindcss'
  ]
})

```


### 建立自訂模組

可以在專案中建立 `modules/` 資料夾，例如：

`modules/example.ts`

```ts
export default defineNuxtModule({
  meta: {
    name: 'example',
    configKey: 'example'
  },
  defaults: {
    addPlugin: true
  },
  setup(options, nuxt) {
    if (options.addPlugin) {
      nuxt.options.plugins.push('~/plugins/example')
    }
  }
})

```

在 `nuxt.config.ts` 啟用：

```ts
export default defineNuxtConfig({
  modules: [
    '~/modules/example'
  ]
})

```