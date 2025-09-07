## 基本介紹
- **Corepack** 是 Node.js 16+ 內建的一個工具，用來管理[[套件管理器]]的版本（[[yarn 基本介紹與指令|yarn]] / [[pnpm 基本介紹與指令|pnpm]] / [[bun 基本介紹與指令|bun]] 等）。
- 特色：
  - 自動下載、啟用對應版本的[[套件管理器]]
  - 避免團隊不同開發者使用不同版本造成依賴問題

---

# 核心指令

## 啟用 Corepack

```bashj
corepack enable
```

# 準備並啟用指定版本

```bash
corepack prepare yarn@stable --activate

corepack prepare pnpm@7.35.0 --activate

corepack prepare bun@1.10.0 --activate
```