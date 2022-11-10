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
        <div class="contentwrapper">
          <SavedModal
            :id="key"
            v-show="showModal"
            @close-modal="showModal = false"
          />
          <div class="videocard" @click="playVid">
            <ul
              v-for="(item, index) in tvvideo"
              v-bind:key="item"
              v-on:click="key = item[0].key"
            >
              <div class="imgs">
                <img
                  :src="path + tvinfo[index].backdrop_path"
                  class="thumbnail"
                />
                <div class="play">
                  <img src="../../../assets/play.svg" />
                </div>
              </div>
              <li>
                <span class="tvtitle">{{ tvinfo[index].name }}</span> <br />
                {{ item[0].name }}
              </li>
            </ul>
          </div>
        </div>
      </div>
      <div v-if="toggletrailertv">
        <div class="contentwrapper">
          <SavedModal
            :id="key"
            v-show="showModal"
            @close-modal="showModal = false"
          />
          <div class="videocard" @click="playVid">
            <ul
              v-for="(item, index) in tvvideo"
              v-bind:key="item"
              v-on:click="key = item[0].key"
            >
              <div class="imgs">
                <img
                  :src="path + tvinfo[index].backdrop_path"
                  class="thumbnail"
                />
                <div class="play">
                  <img src="../../../assets/play.svg" />
                </div>
              </div>
              <li>
                <span class="tvtitle">{{ tvinfo[index].name }}</span> <br />
                {{ item[0].name }}
              </li>
            </ul>
          </div>
        </div>
      </div>
      <div v-if="toggletrailerrent">
        <div class="contentwrapper">
          <SavedModal
            :id="key"
            v-show="showModal"
            @close-modal="showModal = false"
          />
          <div class="videocard" @click="playVid">
            <ul
              v-for="(item, index) in movievideo"
              v-bind:key="item"
              v-on:click="key = item[0].key"
            >
              <div class="imgs">
                <img
                  :src="path + movieinfo[index].backdrop_path"
                  class="thumbnail"
                />
                <div class="play">
                  <img src="../../../assets/play.svg" />
                </div>
              </div>
              <li>
                <div class="movietitle">{{ movieinfo[index].title }}</div>
                <div class="vidname">{{ item[0].name }}</div>
              </li>
            </ul>
          </div>
        </div>
      </div>
      <div v-if="toggletrailermovie">
        <div class="contentwrapper">
          <SavedModal
            :id="key"
            v-show="showModal"
            @close-modal="showModal = false"
          />
          <div class="videocard" @click="playVid">
            <ul
              v-for="(item, index) in movievideo"
              v-bind:key="item"
              v-on:click="key = item[0].key"
            >
              <div class="imgs">
                <img
                  :src="path + movieinfo[index].backdrop_path"
                  class="thumbnail"
                />
                <div class="play">
                  <img src="../../../assets/play.svg" />
                </div>
              </div>
              <li>
                <div class="movietitle">{{ movieinfo[index].title }}</div>
                <div class="vidname">{{ item[0].name }}</div>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import axios from 'axios'

export default {
  name: 'LatestTrailers',
  data() {
    return {
      toggletrailerstream: true,
      toggletrailertv: false,
      toggletrailerrent: false,
      toggletrailermovie: false,
      showModal: false,
      path: 'https://image.tmdb.org/t/p/original',
      youtube: 'https://www.youtube.com/watch?v=',
      tvvideo: [],
      tvinfo: [],
      movievideo: [],
      movieinfo: [],
      key: '',
    }
  },
  mounted() {
    this.fetchTvInfo()
    this.fetchTvVideo()
    this.fetchTvInfo()
    this.fetchMovieInfo()
    this.fetchMovieVideo()
    this.fetchMovieInfo()
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
    fetchTvVideo() {
      const tvid = [95403, 114410, 60625, 83867, 1402, 90462]
      tvid.forEach((element) => {
        axios
          .get(
            `https://api.themoviedb.org/3/tv/${element}/videos?api_key=981dbad49a061dd0de11f31b655cff9b&language=en-US`
          )
          .then((res) => {
            this.tvvideo.push(res.data.results)
          })
      })
    },
    fetchTvInfo() {
      const tvid = [95403, 114410, 60625, 83867, 1402, 90462]
      tvid.forEach((element) => {
        axios
          .get(
            `https://api.themoviedb.org/3/tv/${element}?api_key=981dbad49a061dd0de11f31b655cff9b&language=en-US`
          )
          .then((res) => {
            this.tvinfo.push(res.data)
          })
      })
    },
    fetchMovieVideo() {
      const movieid = [505642, 497828, 900667, 705996, 964909, 664469]
      movieid.forEach((element) => {
        axios
          .get(
            `https://api.themoviedb.org/3/movie/${element}/videos?api_key=981dbad49a061dd0de11f31b655cff9b&language=en-US`
          )
          .then((res) => {
            this.movievideo.push(res.data.results)
          })
      })
    },
    fetchMovieInfo() {
      const movieid = [505642, 497828, 900667, 705996, 964909, 664469]
      movieid.forEach((element) => {
        axios
          .get(
            `https://api.themoviedb.org/3/movie/${element}?api_key=981dbad49a061dd0de11f31b655cff9b&language=en-US`
          )
          .then((res) => {
            this.movieinfo.push(res.data)
          })
      })
    },
    playVid() {
      this.showModal = true
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
    url('../../../assets/trailer.jpeg');
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

.contentwrapper {
  width: max-content;
  height: max-content;
  overflow: auto;
  backface-visibility: hidden;
}

.videocard {
  display: flex;
  justify-content: center;
  text-align: center;
  padding-bottom: 10px;
  background: none;
}

.videocard li {
  list-style: none;
  background: none;
}

.imgs {
  display: grid;
  width: 300px;
  height: 170px;
  grid-template-columns: 24px 1fr 1fr 1fr;
  grid-template-rows: 10px 1fr 1fr 1fr;
  cursor: pointer;
}

.thumbnail {
  width: 300px;
  border-radius: 20px;
}

.play {
  color: white;
  width: 64px;
  grid-area: 3 / 3;
}

.tvtitle {
  padding-top: 10px;
  font-size: 19px;
  font-weight: 700;
}
</style>
