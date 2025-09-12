- **定義**：將 CSS 拆成「最小單位」的 class，每個 class 只做一件事
    
- **目標**：快速、可組合、減少自訂 CSS
    
- **概念**：CSS class 命名與功能一對一，例如：
    
    - `text-center` → 文字置中
        
    - `bg-red-500` → 背景紅色
        
    - `p-4` → padding 1rem

## 優點

- **快速開發**：不用再寫自訂 CSS，直接在 HTML 組合 class
    
- **統一風格**：同一個 class 全專案統一

## 缺點

- **可讀性**：HTML class 會變長
    
- **維護**：大量 class 組合可能難以管理

# 常見框架

- [[Tachyons]]：早期流行的原子化 CSS 框架，開創小而獨立 class 的先例。
- [[Tailwind CSS]]：目前最受歡迎的實用工具優先（utility-first）框架，提供大量預定義原子 class，並通過 [[PostCSS 基本介紹與指令|PostCSS]] 插件優化最終輸出。
- [[UnoCSS]]：下一代原子化 CSS 解決方案，支持按需即時生成，兼容多種預設並具備極高的靈活性。