<template>
  <div class="wrapper">
    <div class="logo">
        <img src="../../assets/TMDB_logo_square.svg" />
        <button>JOIN THE COMMUNITY</button>
    </div>
    <div class="menu">
      <div>
        <ul>
          <li class="title">THE BASICS</li>
          <li>About TMDB</li>
          <li>Contact Us</li>
          <li>Support Forums</li>
          <li>API</li>
          <li>System Status</li>
        </ul>
      </div>
      <div>
        <ul>
          <li class="title">GET INVOLVED</li>
          <li>Contribution Bible</li>
          <li>Add New Movie</li>
          <li>Add New TV Show</li>
        </ul>
      </div>
      <div>
        <ul>
          <li class="title">COMMUNITY</li>
          <li>Guidelines</li>
          <li>Discussions</li>
          <li>Leaderboard</li>
          <li>Twitter</li>
        </ul>
      </div>
      <div>
        <ul>
          <li class="title">LEGAL</li>
          <li>Terms of Use</li>
          <li>API Terms of Use</li>
          <li>Privacy Policy</li>
        </ul>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'PageFooter',
}
</script>
<style scoped>
.wrapper {
  padding: 0 40px;
  background-color: rgba(3 37 65);
  display: flex;
  justify-content: center;
}

.logo {
  margin-top: 50px;
  display: flex;
  flex-direction: column;
}

.logo button {
  background-color: white;
  color: #01b4e4;
  border: none;
  border-radius: 5px;
  padding: 10px 16px;
  font-weight: 600;
  font-size: 17px;
}

.logo img {
  width: 130px;
  margin-left: auto;
  margin-right: 0;
  margin-bottom: 40px;
}

.menu {
  padding: 80px 0;
  display: flex;
  color: white;
  font-size: 18px;
  font-weight: 400;
}

.menu li {
  list-style: none;
}

.title {
  font-weight: 800;
  margin: 0;
}
</style>
