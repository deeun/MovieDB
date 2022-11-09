<template>
  <div class="wrapper">
    <div class="contents">
      <div class="header">
        <h2>Latest Trailers</h2>
        <div class="toggle">
          <div id="trailerstream" class="selected" @click="toggleTrailerStream">
            <span>Streaming</span>
          </div>
          <div id="trailertv" class="notselected" @click="toggleTrailerTv">
            <span>On TV</span>
          </div>
          <div id="trailerrent" class="notselected" @click="toggleTrailerRent">
            <span>For Rent</span>
          </div>
          <div
            id="trailermovie"
            class="notselected"
            @click="toggleTrailerMovie"
          >
            <span>In Theaters</span>
          </div>
        </div>
      </div>
      <div v-if="toggletrailerstream">
        <TrailerStreaming />
      </div>
      <div v-if="toggletrailertv">
        <TrailerTV />
      </div>
      <div v-if="toggletrailerrent">
        <TrailerRent />
      </div>
      <div v-if="toggletrailermovie">
        <TrailerMovie />
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      toggletrailerstream: true,
      toggletrailertv: false,
      toggletrailerrent: false,
      toggletrailermovie: false,
    }
  },
  methods: {
    toggleTrailerStream() {
      this.toggletrailerstream = true
      this.toggletrailertv = false
      this.toggletrailerrent = false
      this.toggletrailermovie = false

      document.getElementById('trailerstream').className = 'selected'
      document.getElementById('trailertv').className = 'notselected'
      document.getElementById('trailerrent').className = 'notselected'
      document.getElementById('trailermovie').className = 'notselected'
    },
    toggleTrailerTv() {
      this.toggletrailerstream = false
      this.toggletrailertv = true
      this.toggletrailerrent = false
      this.toggletrailermovie = false

      document.getElementById('trailerstream').className = 'notselected'
      document.getElementById('trailertv').className = 'selected'
      document.getElementById('trailerrent').className = 'notselected'
      document.getElementById('trailermovie').className = 'notselected'
    },
    toggleTrailerRent() {
      this.toggletrailerstream = false
      this.toggletrailertv = false
      this.toggletrailerrent = true
      this.toggletrailermovie = false

      document.getElementById('trailerstream').className = 'notselected'
      document.getElementById('trailertv').className = 'notselected'
      document.getElementById('trailerrent').className = 'selected'
      document.getElementById('trailermovie').className = 'notselected'
    },
    toggleTrailerMovie() {
      this.toggletrailerstream = false
      this.toggletrailertv = false
      this.toggletrailerrent = false
      this.toggletrailermovie = true

      document.getElementById('trailerstream').className = 'notselected'
      document.getElementById('trailertv').className = 'notselected'
      document.getElementById('trailerrent').className = 'notselected'
      document.getElementById('trailermovie').className = 'selected'
    },
  },
}
</script>
<style scoped>
.wrapper {
  background-position: top center;
  background-size: cover;
  background-repeat: no-repeat;
  color: white;
  overflow: auto;
  box-sizing: border-box;
  background-image: linear-gradient(
      to right,
      rgba(3 37 65 / 80%) 100%,
      rgba(3 37 65 / 0%) 100%
    ),
    url('../assets/trailer.jpeg');
}

.contents {
    min-height: 354px;
}

.header {
  padding: 10px 40px;
  display: flex;
  align-items: center;
}

.contents h2 {
  padding-right: 20px;
}

.toggle {
  display: flex;
  border: 1px solid #1ed5a9;
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
  background: linear-gradient(to right, #c0fecf 0%, #1ed5a9 100%);
  color: black;
}

.notselected {
  background-color: transparent;
}
</style>
