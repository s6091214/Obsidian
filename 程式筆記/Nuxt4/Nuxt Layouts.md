- 用來定義頁面共用的版型
- 例如：導覽列、側邊欄、頁尾
- 可以避免每個頁面重複寫相同的結構

## 建立 Layout
- 在 `layouts/` 資料夾中新增檔案：
  - `layouts/default.vue` → 預設 layout
  - `layouts/admin.vue` → 自訂 layout

## 使用 Layout

在頁面元件（`pages/`）中指定 layout：

- 命名規則kebab-case（烤肉串命名法）
- `layouts/adminLayout.vue` → 名稱是 admin-layout
- 沒寫預設會使用default

```vue
<script setup>
definePageMeta({
  layout: 'admin-layout'
})
</script>

```


## 動態切換 Layout

也可以透過程式動態指定，例如依使用者角色切換。


```vue
<script setup>
definePageMeta({
  layout: () => user.value.isAdmin ? 'admin' : 'default'
})
</script>

```


# 禁用 Layout

```vue
<script setup>
definePageMeta({
  layout: false
})
</script>
```