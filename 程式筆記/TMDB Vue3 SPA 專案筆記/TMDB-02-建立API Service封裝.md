# TMDB Vue3 SPA 專案 - 第 02 步：建立 API Service 封裝

## 目的
封裝 TMDB API 請求，使前端呼叫統一、方便維護，並使用 TypeScript 型別提高開發安全性。

---

## 步驟

### 1️⃣ 安裝 axios
```bash
npm install axios
```

2️⃣ 建立 `src/services/tmdb.ts`
TMDB API 同時接受 **query string 的 api_key** 或 **Bearer Token**
第一種授權方式

```ts
import axios from 'axios'

const apiKey = import.meta.env.VITE_TMDB_API_KEY
const baseUrl = import.meta.env.VITE_TMDB_BASE_URL

const tmdb = axios.create({
  baseURL: baseUrl,
  params: {
    api_key: apiKey,
  }
})

export default tmdb

```

第2種授權方式

```ts
import axios from 'axios'

const baseUrl = import.meta.env.VITE_TMDB_BASE_URL
const token = import.meta.env.VITE_TMDB_BEARER_TOKEN

const tmdb = axios.create({
  baseURL: baseUrl,
  headers: {
    accept: 'application/json',
    Authorization: `Bearer ${token}`,
  },
})
```

3️⃣ 建立常用 API 方法
例如熱門電影、搜尋電影、電影詳情：

```ts
// 取得熱門電影
export const getPopularMovies = (page = 1) =>
  tmdb.get('/movie/popular', { params: { page } })

// 搜尋電影
export const searchMovies = (query: string, page = 1) =>
  tmdb.get('/search/movie', { params: { query, page } })

// 取得電影詳情
export const getMovieDetail = (id: number) =>
  tmdb.get(`/movie/${id}`)

```