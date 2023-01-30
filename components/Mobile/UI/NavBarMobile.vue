<template>
  <nav class="nav">
    <ul class="nav-1">
      <li>hamburger</li>
      <li>LOGO</li>
      <li>person</li>
      <li><img src="../../assets/search.svg" width="22.4" /></li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: 'NavBarMobile',
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
</style>
