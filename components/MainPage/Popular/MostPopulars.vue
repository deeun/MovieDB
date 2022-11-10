<template>
  <div class="wrapper">
    <div class="title">
      <h2>What's Popular</h2>
      <div class="toggle">
        <div id="showtv" class="selected" @click="toggleShowTv">
          <span>On Tv</span>
        </div>
        <div id="showmovie" class="notselected" @click="toggleShowMovie">
          <span>In Theaters</span>
        </div>
      </div>
    </div>
    <div v-if="toggletv">
      <PopularTV />
    </div>
    <div v-if="togglemovie">
      <PopularMovie />
    </div>
  </div>
</template>

<script>
import PopularTV from './PopularTV.vue';
import PopularMovie from './PopularMovie.vue';

export default {
  name : "MostPopulars",
  components : { PopularTV, PopularMovie },
  data() {
    return {
      toggletv: true,
      togglemovie: false,
    }
  },
  methods: {
    toggleShowTv() {
      this.toggletv = true
      this.togglemovie = false

      document.getElementById('showtv').className = 'selected'
      document.getElementById('showmovie').className = 'notselected'
    },
    toggleShowMovie() {
      this.toggletv = false
      this.togglemovie = true

      document.getElementById('showtv').className = 'notselected'
      document.getElementById('showmovie').className = 'selected'
    },
  },
}
</script>
<style scoped>
.wrapper {
    padding: 0 40px;
}

.title {
  display: flex;
  align-items: center;
  margin: 0;
}

.title h2 {
    margin-right: 20px;
}

.toggle {
  display: flex;
  border: solid 1px rgba(3 37 65);
  border-radius: 30px;
  height: 28px;
  width: max-content;
}

.toggle div {
  display: inline-flex;
  align-content: center;
  align-items: center;
  justify-content: center;
  font-size: 1rem;
  padding: 4px 20px;
  margin-bottom: 0;
  border-radius: 30px;
  max-width: max-content;
  font-weight: 700;
}

.selected {
  background-color: #032541;
}

.notselected {
  background-color: transparent;
}

.selected span {
  background: linear-gradient(to right, #c0fecf 0%, #1ed5a9 100%);
  color: transparent;
  background-clip: text;
}
</style>
