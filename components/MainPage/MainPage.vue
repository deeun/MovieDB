<template>
  <div class="wrapper">
    <div v-if="!isMedia">
      <NavBar/>
    </div>
    <div v-if="isMedia">
      <NavBarMobile />
    </div>
    <SearchArea/>
    <MostPopulars/>
    <FreeWatch/>
    <LatestTrailers/>
    <TrendingVids/>
    <JoinToday/>
    <PageFooter/>
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
import NavBarMobile from "~/components/Mobile/UI/NavBarMobile.vue";

export default {
  name: 'MainPage',
  components: {NavBar, SearchArea, MostPopulars, FreeWatch, LatestTrailers, TrendingVids, JoinToday, PageFooter, NavBarMobile},
  methods: {}
}
</script>
<script setup>
const deviceWidth = window.outerWidth
let isMedia = false
if (deviceWidth < 800) {
  isMedia = true
} else {
  isMedia = false
}

const print = () => {
  console.log(deviceWidth)
}
print()
</script>
