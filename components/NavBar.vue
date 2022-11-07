<template>
  <nav class="nav">
    <ul class="nav-1">
      <li><img src="../assets/TMDB_logo.svg" width="154px" /></li>
      <li>Movies</li>
      <li>TV Shows</li>
      <li>People</li>
      <li>More</li>
    </ul>
    <ul class="nav-2">
      <li><img src="../assets/plus.svg" width="22.4" /></li>
      <li><div class="lang">EN</div></li>
      <li>Login</li>
      <li>Join TMDB</li>
      <li><img src="../assets/search.svg" width="22.4" /></li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: 'NavBar',
}
</script>

<style scoped>
.nav {
  display: flex;
  align-items: center;
  justify-content: space-between;
  background-color: #032541;
  color: white;
  height: 64px;
  padding-left: 40px;
  padding-right: 40px;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 10;
  transition: top 0.2s linear;
}

.nav ul {
  display: flex;
  align-items: center;
  justify-content: space-between;
  list-style: none;
}

.nav-1 {
  width: 40%;
}

.nav-2 {
  width: 20%;
}

.lang {
  border: 1px solid;
  border-radius: 3px;
  width: 28px;
  height: 26px;
  text-align: center;
  line-height: 26px;
}
</style>
