## 基本介紹

- 用來管理 **應用層級** 的設定（非環境變量）。
- 適合放「**不會因環境不同而改變**」的設定，例如主題顏色、UI 風格、全域開關。
- 在 **client / server 兩端都能存取**。
- [官方文件](https://nuxt.com/docs/4.x/guide/directory-structure/app/app-config)

## 設定 (`app.config.ts`)

在專案根目錄新增 `app.config.ts`：

```ts
export default defineAppConfig({
  theme: {
    primaryColor: '#007bff',
    darkMode: false
  },
})

```

## 使用 (`useAppConfig`)

在組件或 composable 中使用：

```vue
<script setup lang="ts">
const appConfig = useAppConfig()

console.log(appConfig.theme) 
</script>

