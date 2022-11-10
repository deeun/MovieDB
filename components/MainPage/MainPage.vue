<template>
  <div class="wrapper">
    <NavBar />
    <SearchArea />
    <MostPopulars />
    <FreeWatch />
    <LatestTrailers />
    <TrendingVids />
    <JoinToday />
    <PageFooter />
  </div>
</template>
<script>
import NavBar from '../UI/NavBar.vue'
import FreeWatch from '../MainPage/Free/FreeWatch.vue'
import PageFooter from '../UI/PageFooter.vue'
import LatestTrailers from './Trailer/LatestTrailers.vue'
import MostPopulars from './Popular/MostPopulars.vue'
import SearchArea from './SearchArea.vue'
import TrendingVids from './Trending/TrendingVids.vue'
import JoinToday from './JoinToday.vue'

export default {
  name: 'MainPage',
  components: { NavBar, SearchArea, MostPopulars, FreeWatch, LatestTrailers, TrendingVids, JoinToday, PageFooter },
}
</script>
