## 基本介紹
- **npm** = Node Package Manager
- Node.js 內建套件管理工具，用於：
  - 安裝、管理、更新 JavaScript/Node.js 套件
  - 建立專案的 `package.json` / `package-lock.json`

---

##  安裝

- Node.js 安裝後會自動帶 npm
```bash
node -v   # 查看 Node.js 版本
npm -v    # 查看 npm 版本
npm install -g npm # 全域安裝最新版
```

# 常用指令

```bash
node app.js         # 執行 JS 檔
npm init -y         # 初始化專案
npm install <pkg>   # 安裝套件
npm uninstall <pkg> # 移除套件
npm run <script>    # 執行 package.json scripts
```

# npm 常用簡寫

```bash
npm i <pkg>           # = npm install <pkg>
npm i -D <pkg>        # = npm install --save-dev <pkg>
npm i -g <pkg>        # 全域安裝
npm un <pkg>          # = npm uninstall <pkg>
npm up                # = npm update
npm ls                # 列出已安裝套件

```