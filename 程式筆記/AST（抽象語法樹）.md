## 介紹

-  [講解](https://www.youtube.com/watch?v=meKcyr-oW9Y)
- **抽象語法樹 (Abstract Syntax Tree, AST)** 是一種資料結構。
- 用來表示程式碼的語法結構。
- 編譯器、語言工具、[[Lint]]、轉譯器（如 Babel、[[ESLint 基本介紹與指令|ESLint]]、TypeScript）都會用到。

## 特點
- **樹狀結構**：每個節點代表程式的一部分（變數、函式、運算式…）。
- **抽象化**：不會保留所有原始碼細節（如註解、排版）。
- **可操作性**：方便程式分析、轉換、優化。

# 範例

程式碼：

```js
const x = 5 + 3;
console.log(x);
```

## 轉成 AST（抽象語法樹）

電腦先把程式碼解析成樹狀結構，像這樣（簡化示意）：

```scss
Program
 ├─ VariableDeclaration (const x = 5 + 3)
 │   ├─ Identifier (x)
 │   └─ BinaryExpression (+)
 │       ├─ Literal (5)
 │       └─ Literal (3)
 └─ ExpressionStatement
     └─ CallExpression (console.log(x))
         └─ Identifier (x)
```

- **Program** → 整個程式
    
- **VariableDeclaration** → 變數宣告
    
- **BinaryExpression** → 運算式
    
- **CallExpression** → 函式呼叫

  AST 就像程式碼的「地圖」，電腦看這張地圖才知道程式邏輯。

簡單比喻：

- **SCSS** → AST → CSS
    
- **JS** → AST → 舊版 JS

## 常見應用

- **編譯器 / 轉譯器**：將高階語言轉成機器碼或其他語言（例：Babel 將 ES6 轉 ES5）。
    
- **靜態分析**：像 [[ESLint 基本介紹與指令|ESLint]] 透過 AST 分析程式規則。
    
- **程式碼格式化**：[[Prettier 基本介紹與指令|Prettier]] 會根據 AST 重新排版。
    
- **程式碼轉換**：Webpack、Rollup 插件也常用 AST 做優化。
    

## 工具

- **JavaScript**
    
    - Esprima → JS Parser
        
    - [Acorn](https://github.com/acornjs/acorn) → 輕量解析器
        
    - Babel → 提供 AST 解析與轉換
        
    - [ESTree](https://github.com/estree/estree) → JS AST 標準格式
        
- **可視化**
    
    - AST Explorer → 線上工具，可查看程式碼對應的 AST