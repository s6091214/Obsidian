## 基本介紹

- **@nuxt/icon** 是 Nuxt 官方提供的模組，用於快速載入、管理 SVG / Icon。
- 支援本地 icon 檔案或 [[Iconify 筆記]] 線上圖標庫。
- 自動最佳化與快取，避免手動引入與額外設定。
- [官方文件](https://nuxt.com/modules/icon)
- 有使用[[VSCode]]開發可以安裝[Iconify IntelliSense](https://marketplace.visualstudio.com/items?itemName=antfu.iconify)插件，顯示對應圖標。

# 安裝

```bash
npm install -D @nuxt/icon
```

編輯 `nuxt.config.ts`

```ts
export default defineNuxtConfig({
  modules: ['@nuxt/icon']
})
```

# 使用 nuxi 快速安裝

```js
npx nuxi module add icon
```

- 等同於手動安裝套件 + 修改 `nuxt.config.ts`
- 一鍵完成安裝與設定

## 使用範例

```vue
<template>
  <div>
    <Icon name="tabler:home" />
    <Icon name="mdi:account" size="32" color="red" />
  </div>
</template>

```

### 使用本地 SVG icon

將圖標放在 `~/assets/icons/` 目錄下，例如 `star.svg`：

```vue
<template>
  <Icon name="star" />
</template>

```

## 常用屬性

- `name`：指定 icon 名稱
- `size`：設定大小（數字或單位：`px` / `em` / `rem`，預設 `px`）
- `color`：設定顏色

```vue
<Icon name="mdi:heart" size="48" color="hotpink" />
```