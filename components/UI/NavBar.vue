<template>
  <nav class="nav">
    <ul class="nav-1">
      <li><img src="../../assets/TMDB_logo.svg" width="154px" /></li>
      <li>Movies</li>
      <li>TV Shows</li>
      <li>People</li>
      <li>More</li>
    </ul>
    <ul class="nav-2">
      <li><img src="../../assets/plus.svg" width="22.4" /></li>
      <li><div class="lang">EN</div></li>
      <li>Login</li>
      <li>Join TMDB</li>
      <li><img src="../../assets/search.svg" width="22.4" /></li>
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
  position: fixed;
  width: 100%;
  top: 0;
  left: 0;
  z-index: 10;
  transition: top 0.2s linear;
}

.nav ul {
  padding: 0 40px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  list-style: none;
}

.nav-1 {
  width: 40%;
}

.nav-1 li {
  padding-right: 40px;
}

.nav-2 {
  width: 30%;
  margin: 0;
  padding: 0;
}

.nav-2 li {
  min-width: max-content;
  padding-left: 15px;
}

.lang {
  border: 1px solid;
  border-radius: 3px;
  width: 28px;
  height: 26px;
  text-align: center;
  line-height: 26px;
  font-size: 13px;
}
</style>
