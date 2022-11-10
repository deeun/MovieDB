## The Movie DB with Nuxt 🧚‍♀️

The Movie DB 메인화면 클론코딩 해보기 <br/>
(https://www.themoviedb.org/)

### Build Setup

```bash
# dependency 설치
$ npm install

# port 3000에서 실행
$ npm run dev
```

### File Tree

```
📦components
 ┣ 📂MainPage
 ┃ ┣ 📂Free
 ┃ ┃ ┣ 📜FreeMovie.vue
 ┃ ┃ ┣ 📜FreeTV.vue
 ┃ ┃ ┗ 📜FreeWatch.vue
 ┃ ┣ 📂Popular
 ┃ ┃ ┣ 📜MostPopulars.vue
 ┃ ┃ ┣ 📜PopularMovie.vue
 ┃ ┃ ┗ 📜PopularTV.vue
 ┃ ┣ 📂Trailer
 ┃ ┃ ┗ 📜LatestTrailers.vue
 ┃ ┣ 📂Trending
 ┃ ┃ ┣ 📜TrendingToday.vue
 ┃ ┃ ┣ 📜TrendingVids.vue
 ┃ ┃ ┗ 📜TrendingWeek.vue
 ┃ ┣ 📜JoinToday.vue
 ┃ ┣ 📜MainPage.vue
 ┃ ┗ 📜SearchArea.vue
 ┗ 📂UI
 ┃ ┣ 📜NavBar.vue
 ┃ ┣ 📜PageFooter.vue
 ┃ ┗ 📜SavedModal.vue
```

### 완성 화면
![screencapture-localhost-3000-2022-11-10-15_36_55](https://user-images.githubusercontent.com/102015738/201018660-424eb32e-d767-429c-a5ab-7c676db9caf1.png)


### 추후 과제
- 도넛 원형 차트 만들어보기
- 반응형 미디어쿼리 적용해보기
- 상세페이지 만들어보기
