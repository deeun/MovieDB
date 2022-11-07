<template>
  <div class="wrapper">
    <NavBar />
    <SearchArea />
    <MostPopular />
  </div>
</template>
<script>
import MostPopular from './MostPopular.vue';
import NavBar from './NavBar.vue';
import SearchArea from './SearchArea.vue';

export default {
    name: "MainPage",
    components: { SearchArea, NavBar, MostPopular }
}
</script>