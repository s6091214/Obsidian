- 可重複使用的 **組合式函式**（Composition API functions）
- 用來抽離邏輯，讓不同元件可以共享
- 概念類似 React 的 hooks

---

## 建立 檔案
- 檔案放在 `composables/` 資料夾中
- Nuxt 會自動載入（不需要 `import`）
- **預設只會掃描目錄下的最上層檔案**
  - 例如：`composables/useCounter.ts`、`composables/useUser.ts`  
  - **函式名稱必須以 `use` 開頭**，才能被自動匯入
  - 可以安裝 **[[VueUse]]** 來節省開發時間，直接使用現成的組合式函式

---
# 客製化掃描方式
如果你希望掃描子資料夾或自訂檔案結構，可以在 `nuxt.config.ts` 中修改：

```ts
export default defineNuxtConfig({
  imports: {
    dirs: [
      // 扫描顶级组合函数
      '~/composables',
      // ... 或扫描嵌套一级深度的特定名称和文件扩展名的组合函数
      '~/composables/*/index.{ts,js,mjs,mts}',
      // ... 或扫描给定目录中的所有组合函数
      '~/composables/**'
    ]
  }
})

```

### 注意事項

1. 如果使用 `'~/composables/**'`，會掃描所有檔案，可能會和前兩個規則重複，增加編譯時間。
    
2. **函式名稱必須以 `use` 開頭**。
    
3. 若要在子資料夾管理，可以用 `index.ts` 作為層級入口：

```js
composables/
  ├─ ui/
  │   └─ index.ts
  └─ form/
      └─ index.ts

```
