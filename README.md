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

### 시연 영상
https://www.youtube.com/watch?v=vX4IrLObCMk 

### 추후 과제
- 도넛 원형 차트 만들어보기
(각 미디어별 사용자 평점 부분을 도넛 차트로 표현했어야하는데 구현이 어려워서 우선은 숫자만 표기해두었음)
- 반응형 미디어쿼리 적용해보기
- 상세페이지 만들어보기
- 컴포넌트 재사용성 높여보기 (토글버튼 등)

### 느낀 점
Vue는 처음 사용해보는데 굉장히 새롭고 재밌었다. <br/>
Nuxt 프레임워크도 낯설었지만, 이전에 리액트 프로젝트에서 사용해본 Next와 비슷해서 어느정도 사용할 수 있었다. <br/>
v-if, v-for 등 Vue의 디렉티브 사용법이 흥미로웠다. <br/>
vue에 더 익숙했으면 코드를 더 잘 짤 수 있었을텐데 하는 아쉬움이 남는다. <br/>
앞으로도 계속해서 열공하기 ✏️
