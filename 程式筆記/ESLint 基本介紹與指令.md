
- [官網](https://eslint.org/)
    
- 功能：
    
    - 找出程式中的 **錯誤 / 潛在問題**
        
    - 維持 **程式碼風格一致性**
        
    - 可搭配編輯器（[[VSCode]] 等）即時提示

# 常用指令

```bash 
npm install eslint --save-dev # 安裝在本地環境
npx eslint --init # 初始化設定
npx eslint .              # 檢查所有檔案
npx eslint src/           # 檢查 src 資料夾
npx eslint --fix .        # 自動修復可修復的問題
npm install --save-dev @typescript-eslint/parser @typescript-eslint/eslint-plugin
```

## 搭配工具

- [[Prettier 基本介紹與指令|Prettier]] → 負責程式碼格式化
    
- [[VSCode]] → 安裝 ESLint 插件可即時檢查

# 範例 9.3.5版本

``` js
// @ts-check

import withNuxt from './.nuxt/eslint.config.mjs';

import prettier from 'eslint-plugin-prettier';

  

export default withNuxt({

  files: ['**/*.{js,ts,vue}'], // 檢查所有 JS、TS、Vue 檔案

  plugins: {

    prettier: prettier,

  },

  rules: {

    'prettier/prettier': 'error', // 格式不符直接報錯

    'no-console': 'warn', // 使用 console 只警告

  },

});
```