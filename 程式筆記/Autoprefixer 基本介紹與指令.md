## 官網
- [GitHub](https://github.com/postcss/autoprefixer)

## 介紹
- 基於 **[[PostCSS 基本介紹與指令]]** 的插件。
- 自動為 CSS 新屬性加上瀏覽器前綴（例如 `-webkit-`, `-moz-`）。
- 使用 **[[Can I Use]]** 的數據決定哪些前綴需要加。

## 安裝
```bash
npm i -D autoprefixer postcss
```

## 設定方式

在 `postcss.config.js` 中新增：

```js
export default {
  plugins: {
    autoprefixer: {}
  }
}
```

## 使用範例

輸入：

```css
:fullscreen a {
  display: flex;
}
```

輸出 (依據瀏覽器清單自動加前綴)：

```css
:-webkit-full-screen a {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
}
```

## 搭配工具

- **[[PostCSS 基本介紹與指令|PostCSS]]** → 作為插件執行。
    
- **Browserslist** → 設定目標瀏覽器，影響 Autoprefixer 行為。
    
- **[[Can I Use]]** → 數據來源。

## 常見應用

- 確保 [[Tailwind CSS]] 或手寫 CSS 在舊版瀏覽器上能正常運作。
    
- 搭配 Vite / Nuxt / Webpack 自動處理 CSS。