<template>
  <div class="wrapper">
    <h1>Join Today</h1>
    <div class="contents">
      <div class="contents1">
        <p>
          Get access to maintain your own <em>custom personal lists, track what
          you've seen</em> and search and filter for <em>what to watch next</em>—regardless if
          it's in theatres, on TV or available on popular streaming services
          like Netflix, Amazon Prime Video, Disney Plus, and wavve.
        </p>
        <button>Sign Up</button>
      </div>
      <div class="contents2">
        <ul>
          <li>Enjoy TMDB ad free</li>
          <li>
            Maintain a personal watchlist Filter by your subscribed streaming
            services and find something to watch
          </li>
          <li>Log the movies and TV shows you've seen</li>
          <li>Build custom lists Contribute to and improve our database</li>
        </ul>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'JoinToday',
}
</script>
<style scoped>
.wrapper {
  padding: 15px 40px;
  background-image: url('../../assets/jointodaybg.jpg');
  background-position: center center;
  background-size: cover;
  background-repeat: no-repeat;
  color: white;
}

.contents {
  display: flex;
  padding-bottom: 20px;
}

.contents1 {
  width: 65%;
  font-size: 19px;
  margin-right: 40px;
}

.contents1 em {
    opacity: 0.7;
}

.contents1 button {
    background-color: #805be7;
    font-size: 16px;
    font-weight: 600;
    color: white;
    padding: 8px 16px;
    border: none;
    border-radius: 5px;
}

.contents2 {
  font-size: 16px;
  margin-left: 20px;
}
</style>
