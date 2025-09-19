# 建立專案

```
npx nuxi@latest init my-app # 安裝最新版
```

# 安裝Nuxt CLI

```bash
 npx nuxi@latest
```

# 常用指令

## 查看版本

```bash
npx nuxi info        # 查看 nuxi/Nuxt 版本
```

## 開發伺服器

```bash
npm run dev
npx nuxi dev                 # 啟動開發伺服器 (預設 port 3000)
npx nuxi dev -p 4000         # 指定 port
npx nuxi dev --https         # 啟用 https (自簽憑證)
```

## 建置 / 預覽 / 生成

```
npx nuxi build               # 建立正式版
npx nuxi preview             # 本地預覽 build 結果
npx nuxi generate            # 產生靜態頁面 (SSG)
```

# 清理快取

```
npx nuxi cleanup             # 清除快取 (.nuxt, node_modules/.cache)
```

## 套件管理 / 升級

```
npm i -D nuxt@3.6.5          # 指定 Nuxt 3 版本安裝
npx nuxt upgrade             # 升級 Nuxt 到最新版本
```

## 開發工具

```
npx nuxt devtools disable    # 關閉 Devtools (預設啟用 enable)
```

## 安裝 [[Prettier 基本介紹與指令|Prettier]] + [[ESLint 基本介紹與指令|ESLint]] 套件

```bash
npm i -D prettier eslint-config-prettier eslint-plugin-prettier
```

# 安裝 [[Tailwind CSS]]

```bash
npm i @nuxtjs/tailwindcss
```

- 在 `nuxt.config.ts` 的 `modules` 中加入：
```ts
modules: ['@nuxtjs/tailwindcss'],
```

# 生成 Tailwind 設定檔

```js
npx tailwindcss init
```
- 這會建立 `tailwind.config.js`
    
- 如果需要自訂主題或 class，可以在裡面設定

# 安裝 Prettier + Tailwind 插件（用於自動排序 class）

- [套件](https://github.com/tailwindlabs/prettier-plugin-tailwindcss?tab=readme-ov-file)

```bash
npm install -D prettier prettier-plugin-tailwindcss
```

# 設定 `.prettierrc.cjs`

```js
  plugins: ['prettier-plugin-tailwindcss'],

  tailwindConfig: './tailwind.config.js', // Tailwind 設定檔（可選）

  tailwindStylesheetPrettier: './assets/css/tailwind.css', // ⚡ 指定 主入口
```

# 新增 [[Tailwind CSS]] 主入口檔案

assets/css/tailwind.css

```css
@tailwind base;

@tailwind components;

@tailwind utilities;
```

- 這個檔案會被 Prettier 插件讀取，才能正確排序 class