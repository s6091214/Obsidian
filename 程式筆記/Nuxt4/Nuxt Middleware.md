## 基本介紹

- Middleware 是在進入某個頁面前執行的函式，可以用來做 **驗證、權限檢查、導向** 等邏輯。
- Nuxt 會在進入頁面或導航切換時自動執行對應的 middleware。

## 建立 Middleware

-  在 `middleware/` 資料夾下建立檔案，例如：

```t
middleware/auth.ts
```

撰寫 middleware 函式：

```ts
export default defineNuxtRouteMiddleware((to, from) => {
  const user = useUserStore()
  if (!user.isLoggedIn) {
    return navigateTo('/login')
  }
})

```

**在頁面上指定**：

```vue
<script setup>
definePageMeta({
  middleware: 'auth'
})
</script>

```

**多個 middleware**：

```ts
definePageMeta({
  middleware: ['auth', 'another']
})
```

**全域 middleware**：

- 檔名加上 `global` 前綴，例如：`middleware/auth.global.ts`
- 所有頁面切換時都會執行。