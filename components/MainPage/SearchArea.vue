<template>
  <div class="search-area">
    <div class="search-area-contents">
      <div class="title">
        <h2>Welcome.</h2>
        <h3>
          Millions of movies, TV shows and people to discover. Explore now.
        </h3>
      </div>
      <form class="example" action="action_page.php">
        <input
          type="text"
          placeholder="Search for a movie, tv show, person..."
          name="search"
        />
        <button type="submit">Search</button>
      </form>
    </div>
  </div>
</template>
<script>
export default {
  name: 'SearchArea',
}
</script>
<style scope>
.search-area {
  margin-top: 64px;
  margin-bottom: 15px;
  background-image: linear-gradient(
      to right,
      rgba(3 37 65 / 80%) 0%,
      rgba(3 37 65 / 0%) 100%
    ),
    url('../../assets/background.jpeg');
  display: flex;
  align-items: center;
  color: white;
  height: calc(100vh / 2.5);
  min-height: 300px;
  max-height: 360px;
  background-position: top center;
  background-size: cover;
  background-repeat: no-repeat;
}

.search-area-contents {
  width: 100%;
  padding: 30px 40px;
}

.title {
  width: 100%;
  margin-bottom: 30px;
}

.search-area-contents form {
  display: flex;
}

.search-area-contents h2 {
  margin: 0;
  padding: 0;
  font-size: 48px;
}

.search-area-contents h3 {
  margin: 0;
  padding: 0;
  font-size: 32px;
}

.search-area-contents input {
  width: 100%;
  border: none;
  border-radius: 20px;
  font-size: 16px;
  padding: 10px 20px;
}

.search-area-contents input:focus {
  outline: none;
}

.search-area-contents button {
  margin-left: -50px;
  border: none;
  border-radius: 20px;
  height: 39.5px;
  font-size: 14px;
  font-weight: 700;
  color: white;
  padding: 10px 26px;
  background: linear-gradient(
    to right,
    rgba(30 213 169 / 100%) 0%,
    rgba(1 180 228 / 100%) 100%
  );
}
</style>
