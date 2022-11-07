<template>
    <div>
       <div>{{ movie.results ? movie.results[0] : "" }}</div>
       <div>{{ tv.results ? tv.results[0] : "" }}</div>
    </div>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      movie: {},
      tv: {}
    }
  },
  created() {
    this.fetchMovie();
    this.fetchTv();
  },
  methods: {
    async fetchMovie() {
      const response = await axios.get('https://api.themoviedb.org/3/movie/popular?api_key=981dbad49a061dd0de11f31b655cff9b&language=en-US&page=1');
      this.movie = response.data;
    },
    async fetchTv() {
      const response = await axios.get('https://api.themoviedb.org/3/tv/popular?api_key=981dbad49a061dd0de11f31b655cff9b&language=en-US&page=1');
      this.tv = response.data;
    }
  },
}
</script>
