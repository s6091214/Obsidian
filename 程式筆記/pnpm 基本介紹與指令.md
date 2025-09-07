## 基本介紹
- **pnpm** 是一個快速、節省磁碟空間的 JavaScript 套件管理工具  
- 特色：
  - 用 **硬連結（hard link）** 共享 node_modules，節省磁碟空間
  - 安裝速度快，依賴隔離更嚴格
  - 支援 monorepo（多專案管理）
  - CLI 與 npm 相似，易上手

---

# 安裝 pnpm

### 全域安裝

```bash
npm install -g pnpm
pnpm -v
```

```

# 常用指令

```bash
pnpm init          # 互動式建立 package.json
pnpm init -y       # 快速建立 package.json
pnpm add <pkg>       # 安裝依賴
pnpm add -D <pkg>    # 安裝開發依賴
pnpm remove <pkg>    # 移除套件
pnpm up <pkg>        # 更新套件
pnpm install         # 安裝 package.json 內所有依賴
pnpm run <script>    # 執行 package.json scripts
pnpm <script>        # 簡寫
pnpm recursive install      # 安裝所有子專案依賴
pnpm recursive run build    # 執行所有子專案 build script
```