## 官網 / 文件
- [官方網站](https://postcss.org/)
- [GitHub Repo](https://github.com/postcss/postcss)

## 介紹
- [[PostCSS 基本介紹與指令|PostCSS]] 是一個 **CSS 處理工具**，可以透過 **插件 (plugins)** 來轉換 CSS。
- 不是框架，而是像 Babel 一樣的「轉換器」。
- 常用於：
  - 加上自動前綴（[[Autoprefixer 基本介紹與指令]]）
  - 支援未來的 CSS 語法
  - 壓縮、優化 CSS

# 安裝

```bash
npm i -D postcss
```

## 設定

建立 `postcss.config.js` 或 `postcss.config.cjs`：

```js
export default {
  plugins: {
    autoprefixer: {},
  },
}
```


## 常見插件

- [[Autoprefixer 基本介紹與指令|autoprefixer|]] → 自動加瀏覽器前綴
    
- `cssnano` → 壓縮 CSS
    
- `postcss-preset-env` → 使用未來 CSS 特性
    
- [[Tailwind CSS]] → Tailwind 就是基於 PostCSS 運行的

## 備註

- 在 Nuxt 3 中，如果你安裝 `@nuxtjs/tailwindcss`，會自動處理 PostCSS。
    
- PostCSS 本身只是一個「平台」，要搭配插件才有功能。