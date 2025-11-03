- **Pinia store** 管理熱門電影資料
- **Vue 組件** 顯示熱門電影列表
- **Tailwind UI** 排版
- **呼叫剛剛封裝的 tmdb.ts API**
- 整合成完整首頁。
 
1️⃣ 建立 Pinia Store
```ts
// src/stores/movie.ts
import { defineStore } from 'pinia'
import { getPopularMovies } from '@/services/tmdb'

export const useMovieStore = defineStore('movie', {
  state: () => ({
    popularMovies: [] as Movie[],
    loading: false
  }),
  actions: {
    async fetchPopularMovies(page = 1) {
      this.loading = true
      try {
        const { data } = await getPopularMovies(page)
        this.popularMovies = data.results
      } finally {
        this.loading = false
      }
    }
  }
})

// TypeScript 型別
export interface Movie {
  id: number
  title: string
  poster_path: string | null
  overview: string
  release_date: string
  vote_average: number
}

```

