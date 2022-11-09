<template>
  <div class="wrapper">
    <div class="videocard">
      <ul v-for="(item, index) in tvvideo2" v-bind:key="item">
        <img :src="path + tvinfo2[index].backdrop_path" class="thumbnail" />
        <li>
          <span class="tvtitle">{{ tvinfo2[index].name }}</span> <br />
          {{ item[0].name }}
        </li>
      </ul>
    </div>
  </div>
</template>
<script>
import axios from 'axios'

export default {
  data() {
    return {
      path: 'https://image.tmdb.org/t/p/original',
      tvvideo: [],
      tvvideo2: [],
      tvinfo: [],
      tvinfo2: [],
    }
  },
  mounted() {
    this.fetchTvInfo()
    this.fetchTvVideo()
    this.fetchTvInfo()
    this.fetchTvVideo()
  },
  methods: {
    fetchTvVideo() {
      const tvid = [95403, 114410, 60625, 83867, 1402, 90462]
      tvid.forEach((element) => {
        axios
          .get(
            `https://api.themoviedb.org/3/tv/${element}/videos?api_key=981dbad49a061dd0de11f31b655cff9b&language=en-US`
          )
          .then((res) => {
            this.tvvideo.push(res.data.results)
            this.tvvideo2 = this.tvvideo
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
            this.tvinfo2 = this.tvinfo
          })
      })
    },
  },
}
</script>
<style scoped>
.wrapper {
  background: none;
  width: max-content;
  height: max-content;
  overflow: auto;
}

.videocard {
  display: flex;
  justify-content: center;
  text-align: center;
  padding-bottom: 10px;
}

.videocard li {
  list-style: none;
}

.thumbnail {
  width: 300px;
  border-radius: 20px;
}

.tvtitle {
  font-size: 19px;
  font-weight: 700;
}
</style>
