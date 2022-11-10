<template>
  <div class="tvbox">
    <li class="cards" v-for="item in tv.results" v-bind:key="item">
      <img :src="path + item.poster_path" class="poster" />
      <div class="percent">
        <div class="percentshow">
          {{ item.vote_average * 10 }}
          <span>%</span>
        </div>
      </div>
      <div class="titledate">
        <span class="name">{{ item.name }}</span> <br />
        <span class="date">
          {{ month[Number(item.first_air_date.slice(5, 7)) - 1] }}
          {{ item.first_air_date.slice(8, 10) }},
          {{ item.first_air_date.slice(0, 4) }}
        </span>
      </div>
    </li>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  data() {
    return {
      path: 'https://image.tmdb.org/t/p/original',
      imgPath: '',
      movie: {},
      tv: {},
      month: [
        'Jan',
        'Feb',
        'Mar',
        'Apr',
        'May',
        'Jun',
        'Jul',
        'Aug',
        'Oct',
        'Nov',
        'Dec',
      ],
    }
  },
  created() {
    this.fetchMovie()
    this.fetchTv()
  },
  methods: {
    async fetchMovie() {
      const response = await axios.get(
        'https://api.themoviedb.org/3/movie/popular?api_key=981dbad49a061dd0de11f31b655cff9b&language=en-US&page=1'
      )
      this.movie = response.data
    },
    async fetchTv() {
      const response = await axios.get(
        'https://api.themoviedb.org/3/tv/popular?api_key=981dbad49a061dd0de11f31b655cff9b&language=en-US&page=1'
      )
      this.tv = response.data
    },
  },
}
</script>
<style scoped>
.tvbox {
  display: flex;
  list-style: none;
  position: relative;
  overflow: auto;
  padding-bottom: 15px;
}

.cards {
  margin-right: 20px;
}

.percent {
  background-color: rgba(3 37 65);
  border: rgba(3 37 65) 2px solid;
  color: white;
  border-radius: 34px;
  height: 34px;
  width: 34px;
  display: flex;
  justify-content: center;
  padding: 0;
  margin: 0;
  top: 205px;
  position: absolute;
  margin-left: 10px;
}

.percentshow {
  border: #21d07a solid 2px;
  border-radius: 30px;
  font-size: 14px;
  font-weight: 700;
  text-align: center;
  align-items: center;
  width: 32px;
  display: flex;
  justify-content: center;
}

.percentshow span {
  font-size: 8px;
  margin: 0;
  padding: 0;
}

.poster {
  width: 150px;
  border-radius: 10px;
  margin-bottom: 20px;
}

.titledate {
  margin-left: 10px;
}

.name {
  font-weight: 700;
}

.date {
    font-size: 14px;
    color: rgba(0 0 0 / 60%)
}
</style>
