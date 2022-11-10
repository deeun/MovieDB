<template>
  <div class="wrapper">
    <div class="title">
      <h2>Trending</h2>
      <div class="toggle">
        <div id="showday" class="selected" @click="toggleShowDay">
          <span>Today</span>
        </div>
        <div id="showweek" class="notselected" @click="toggleShowWeek">
          <span>This Week</span>
        </div>
      </div>
    </div>
    <div v-if="toggleday">
      <TrendingToday />
    </div>
    <div v-if="toggleweek">
      <TrendingWeek />
    </div>
  </div>
</template>
<script>
import TrendingToday from './TrendingToday.vue'
import TrendingWeek from './TrendingWeek.vue'

export default {
  name: 'TrendingVids',
  components: { TrendingToday, TrendingWeek },
  data() {
    return {
      toggleday: true,
      toggleweek: false,
    }
  },
  methods: {
    toggleShowDay() {
      this.toggleday = true
      this.toggleweek = false

      document.getElementById('showday').className = 'selected'
      document.getElementById('showweek').className = 'notselected'
    },
    toggleShowWeek() {
      this.toggleday = false
      this.toggleweek = true

      document.getElementById('showday').className = 'notselected'
      document.getElementById('showweek').className = 'selected'
    },
  },
}
</script>
<style scoped>
.wrapper {
  padding: 0 40px;
  background-image: linear-gradient(
      to top,
      rgba(255 255 255 / 80%) 0%,
      rgba(255 255 255 / 80%)  100%
    ),
    url('../../../assets/trending.svg');
  background-position: 50% 200px;
  background-repeat: no-repeat;
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
