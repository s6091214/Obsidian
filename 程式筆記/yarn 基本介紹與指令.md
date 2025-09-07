## 基本介紹
- **Yarn** 是 Facebook 發展的 JavaScript 套件管理工具
- 特色：
  - 安裝速度快（快取機制）
  - 鎖定版本 (`yarn.lock`) 保證團隊一致性
  - CLI 命令與 npm 相似，但提供額外功能

---

## 安裝 Yarn
### 全域安裝
```bash
npm install -g yarn
yarn -v 
```

# 常用指令

```
yarn init          # 互動式建立 package.json
yarn init -y       # 快速建立 package.json
yarn add <pkg>       # 安裝套件
yarn add -D <pkg>    # 安裝開發套件
yarn remove <pkg>    # 移除套件
yarn upgrade <pkg>   # 更新套件
yarn run <script>    # 執行 package.json scripts
yarn <script>        # 簡寫
yarn install         # 安裝 package.json 內所有依賴
yarn                  # 簡寫同上
yarn cache clean     # 清除快取
yarn why <pkg>       # 查詢套件安裝原因
yarn outdated        # 查看過時套件
```