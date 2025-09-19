## 基本介紹

- Nuxt 提供 `server/` 資料夾來處理 **後端 API 與伺服器邏輯**。
- 不需要額外架設 Express/Koa，直接用 Nuxt 的 **Nitro server** 就能寫 API。
- [官方文件](https://nuxt.com/docs/4.x/guide/directory-structure/server)

# 建立 API Route

在 `server/api/` 下建立檔案，例如：

```ts
server/api/hello.ts
```

```ts
export default defineEventHandler((event) => {
  return { message: 'Hello from server!' }
})
```

存取方式：

- 瀏覽器 / Postman：`http://localhost:3000/api/hello`
- 前端呼叫：

```ts
const { data } = await useFetch('/api/hello')
```

- 要新增沒有`/api`前綴的伺服器路由，請將它們放入`~/server/routes`目錄中。

## 指定請求方法（Method-specific routes）

- 只允許特定的 HTTP method，可以在檔名加上 `.get`、`.post`、`.put`、`.delete`。
    
- 範例：

```ts
server/api/hello.get.ts
```

```ts
export default defineEventHandler(() => {
  return { message: 'This only works with GET' }
})

```
