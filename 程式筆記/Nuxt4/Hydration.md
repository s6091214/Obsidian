## 基本介紹

- **Hydration** 是 SSR（Server-Side Rendering）的一個重要概念。
- 伺服器先生成 **完整 HTML** 傳給瀏覽器，使用者可以立即看到頁面。
- 瀏覽器下載 JS 後，Vue 會把 HTML **「綁定成可互動的組件」** → 這個過程就叫 **Hydration**。

## 特點

1. **畫面快速顯示**
    - 首屏載入快，因為 HTML 已經在伺服器生成。
2. **互動性**
    - 下載 JS 後，Vue 組件才可以響應使用者互動（按鈕點擊、表單綁定等）。
3. **SSR + CSR 結合**
    - Hydration 是 SSR 生成的 HTML + 客戶端 Vue 互動的橋樑。

## 常見問題

-  **console.log 出現兩次**
    - 原因：SSR 階段會先執行一次，Hydration 客戶端再執行一次 → log 出現兩次。
    - 解決方法：

```ts
onMounted(() => {
  console.log('只在客戶端執行')
})
```

**資料同步問題**

- SSR 渲染的資料與客戶端資料不一致會出現「hydration mismatch」警告。
    
- 解決方法：
    - 保證 SSR 與 CSR 使用相同的初始資料
    - 延遲客戶端資料請求到 `onMounted()`