<template>
    <div class="wrapper">
      <div class="title">
        <h2>Free To Watch</h2>
        <div class="toggle">
          <div id="showfreemovie" class="selected" @click="toggleShowMovie">
            <span>Movies</span>
          </div>
          <div id="showfreetv" class="notselected" @click="toggleShowTv">
            <span>TV</span>
          </div>
        </div>
      </div>
      <div v-if="togglefreemovie">
        <FreeMovie />
      </div>
      <div v-if="togglefreetv">
        <FreeTV />
      </div>
    </div>
  </template>
  
  <script>
import FreeMovie from './FreeMovie.vue'
import FreeTV from './FreeTV.vue';

  export default {
    data() {
        return {
            togglefreemovie: true,
            togglefreetv: false,
        };
    },
    methods: {
        toggleShowMovie() {
            this.togglefreemovie = true;
            this.togglefreetv = false;
            document.getElementById("showfreemovie").className = "selected";
            document.getElementById("showfreetv").className = "notselected";
        },
        toggleShowTv() {
            this.togglefreemovie = false;
            this.togglefreetv = true;
            document.getElementById("showfreemovie").className = "notselected";
            document.getElementById("showfreetv").className = "selected";
        },
    },
    components: { FreeMovie, FreeTV }
}
  </script>
  <style scoped>
  .wrapper {
      padding: 15px 40px;
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
  