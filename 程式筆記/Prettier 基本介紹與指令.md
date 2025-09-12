- **官方網站**：[https://prettier.io/](https://prettier.io/)
- **功能**：程式碼格式化工具，支援 JavaScript、TypeScript、HTML、CSS、JSON 等多種語言，保持程式碼風格一致。

# 安裝方式

1. 打開 [[VSCode]] → 插件商店 (`Ctrl + Shift + X`)  
2. 搜尋 **Prettier - Code formatter**  
3. 點選安裝

# 常用指令

```bash
npm install --save-dev prettier
```


# 基本設定

```json
{
  "semi": true,             // 行尾是否加分號
  "singleQuote": true,      // 使用單引號
  "tabWidth": 2,            // Tab 寬度
  "trailingComma": "es5"    // 末尾逗號規則
}
```


# [[VSCode]] 設定

### 在 `settings.json` 加入：

```json
{
  "editor.formatOnSave": true,          // 儲存時自動格式化
  "prettier.requireConfig": true        // 僅在有配置檔時啟用 Prettier
}
```