###  Disallow self-closing on HTML void elements (<input/>)

- 在 `eslint.config.mjs` 的 `rules` 中新增以下設定：

```ts
"vue/html-self-closing": ["error", {
  "html": {
    "void": "always",       // ✅ 允許 <input />、<img />、<br /> 等自閉合
    "normal": "always",    // 一般元素建議自閉合（例如 <div></div> ✅）
    "component": "always"  // Vue 元件允許自閉合（例如 <MyComponent /> ✅）
  },
  "svg": "always",
  "math": "always"
}]

```