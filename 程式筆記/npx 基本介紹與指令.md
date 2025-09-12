# npx 筆記

## 什麼是 npx
- **npx** 是 npm 5.2+ 之後內建的工具
- 用來直接執行套件，不需要全域安裝
- 適合一次性命令或快速建立專案

---

## 常見用途

### 執行 CLI 工具（免安裝）

```bash
npx create-react-app my-app
npx create-vite@latest my-vite-app
npx nuxi@latest init nuxt-app
```

# 與 [[npm 基本介紹與指令|npm]] 的差異
- `npm i -g <pkg>` → 全域安裝，會佔用環境
    
- `npx <pkg>` → 直接執行，結束後不留套件（或使用專案內的版本）

# 檢查 npx 版本

``` bash
npx -v
```

## 清理快取

有時候 `npx` 會快取舊版本的套件，導致指令執行結果不符合預期。  
這時可以用以下方式清理快取：

```bash
npx clear-npx-cache
```