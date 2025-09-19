## 什麼是 VueUse？
- 一個 **組合式函式（composables）工具庫**，基於 Vue 3 Composition API  
- 提供大量現成的函式，例如滑鼠位置、視窗尺寸、localStorage、事件監聽、動畫等  
- 類似 [[Nuxt Composables]]，但功能更多、開箱即用  
- [VueUse 官網](https://vueuse.org/)  
- [教學](https://ithelp.ithome.com.tw/articles/10351156)

---

# 安裝

```bash
npm i @vueuse/core
```

# 範例

```vue
<script setup lang="ts">
import { useMouse } from '@vueuse/core'

const { x, y } = useMouse()
</script>

<template>
  <p>滑鼠位置：{{ x }}, {{ y }}</p>
</template>
```
