## 目的
建立 TMDB API 連線所需的金鑰，作為專案與外部資料來源的橋樑。

---

## 步驟

1. 註冊 TMDB 帳號  
   前往 [TMDB 官方網站](https://www.themoviedb.org/signup) 註冊帳號。

2. 登入並申請 API Key  
   - 登入後，打開 [API 設定頁](https://www.themoviedb.org/settings/api)  
   - 點選「Create」建立新的 API Key  
     - 類型：Developer  
     - 用途：Personal project  
     - 申請摘要範例：`我正在開發一個 Vue 3 + TypeScript 單頁應用程式（SPA），目標是建立一個電影瀏覽網站。專案會使用 TMDB API 取得熱門電影、搜尋電影及顯示電影詳情，並在前端呈現電影封面、標題、評分、上映日期等資訊。此專案僅作為個人學習與練習用途，不會用於商業營利。`  
   - 取得一串 API Key，例如：1234567890abcdef1234567890abcdef
3. -  設定專案環境變數 
   在專案根目錄新增 `.env.local` 檔案，內容：

```ts
VITE_TMDB_API_KEY=你的API金鑰
VITE_TMDB_BASE_URL=https://api.themoviedb.org/3
```

Vue 3 + Vite 專案會自動載入 `VITE_` 開頭的環境變數，建議 `.env.local` 加入 `.gitignore` 保護金鑰安全。

## 完成條件

- 已註冊 TMDB 帳號並登入
- 成功取得 API Key
- `.env.local` 已建立並能在專案中讀取

```ts
const apiKey = import.meta.env.VITE_TMDB_API_KEY

const baseUrl = import.meta.env.VITE_TMDB_BASE_URL

  

console.log('TMDB API Key:', apiKey)

console.log('TMDB Base URL:', baseUrl)
```