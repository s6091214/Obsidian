- **可重複使用的元件**，用來拆分頁面 UI  
- 例如：按鈕、導覽列、表單區塊

---

## 建立 Components
- 在 `components/` 資料夾下建立 Vue 檔案
  - `components/NavBar.vue`
  - `components/Button.vue`

Nuxt 會自動載入（不需要手動 `import`）


## 自動匯入規則

- Nuxt 會自動把 `components/` 裡的檔案轉成 PascalCase (大駝峰命名) 使用
    
    - `components/nav-bar.vue` → `<NavBar />`
        
    - `components/button.vue` → `<Button />`