## 基本介紹
- **Deno** 是 Node.js 作者 **Ryan Dahl** 後來開發的新一代 JavaScript / TypeScript 執行環境。
- 特色：
  - 原生支援 **TypeScript**
  - 預設更安全（需要顯示開啟檔案 / 網路 / 環境存取權限）
  - 內建常用工具（formatter、linter、test runner）
  - 使用 **ES Module**，不需要 `package.json`

---
# 安裝 Deno

- [官網](https://deno.com/)

```powershell
irm https://deno.land/install.ps1 | iex
deno -V # 檢查版本
```

# 常用指令

```bash
deno run app.ts               # 執行程式
deno run --allow-net server.ts # 執行並允許網路存取
deno run --allow-read file.ts  # 執行並允許讀檔
```


# 與 Node.js 差異

- **Node.js** → [[npm 基本介紹與指令]] 生態龐大，需額外安裝 TypeScript、[[lint]]、測試工具
    
- **Deno** → 內建 TS / 測試 / [[lint]]，安全性設計更嚴格
    
- **模組系統**：Node 傳統用 CommonJS/ESM；Deno 全部用 ESM + URL 匯入