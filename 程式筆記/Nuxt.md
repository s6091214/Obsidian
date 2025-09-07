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


