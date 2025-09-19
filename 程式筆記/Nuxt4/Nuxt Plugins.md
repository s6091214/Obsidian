## 基本介紹

Nuxt 的 **Plugins** 機制，可以在 Vue 應用程式初始化之前或之後，  
注入第三方套件、全域功能，或自訂邏輯。  

- Plugins 會在應用啟動時自動載入  
- 可用來註冊 Vue 插件、注入變數或方法到 `nuxtApp`  
- 支援 **Client only / Server only** 載入  

---

# 建立 Plugins

在 `plugins/` 資料夾下建立檔案，例如：

`plugins/scrollto.js`  

```js
import VueScrollTo from 'vue-scrollto';

export default defineNuxtPlugin((nuxtApp) => {

  nuxtApp.vueApp.use(VueScrollTo);

});
```

# 插件載入的順序

- 您可以透過 **檔案命名順序 (字母 / 數字)** 來控制插件的註冊順序。
- 若插件之間有依賴關係，需特別安排載入順序。

```js
plugins/
 | - 01.myPlugin.ts
 | - 02.myOtherPlugin.ts
```