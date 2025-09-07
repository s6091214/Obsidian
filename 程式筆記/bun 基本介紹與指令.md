## 基本介紹
- **Bun** 是一個快速的 JavaScript/TypeScript 執行環境 + [[套件管理器]] + 打包工具。
- [文檔](https://www.bunjs.cn/docs/installation)
- 特色：
  - 超快的啟動與打包速度
  - 原生支援 **TypeScript**
  - 內建 **[[npm 基本介紹與指令|npm]] 相容套件管理**
  - 內建打包器 (bundler)
  - 支援 Node.js API（大部分）  

---

# 常用指令

```bash
bun init          # 互動式建立新專案
bun init my-app   # 指定專案名稱
bun install       # 安裝 package.json 內的依賴
bun add <pkg>     # 安裝單一套件
bun add -d <pkg>  # 安裝開發套件
bun remove <pkg>  # 移除套件
bun upgrade       # 更新依賴
bun run index.js
bun run start    
bun build src/index.ts --outdir dist
```