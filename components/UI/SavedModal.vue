<template>
  <transition name="modal-fade">
    <div class="modal-overlay" @click="$emit('close-modal')">
      <div class="modal">
        <iframe
        width="1000px"
        height="600px"
          :src="link + id"
          title="YouTube video player"
          frameborder="0"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
          allowfullscreen
        ></iframe>
      </div>
    </div>
  </transition>
</template>

<script>
export default {
  props: ['id'],
  data() {
    return {
      link: "https://www.youtube.com/embed/"
    }
  },
}
</script>

<style scoped>
.modal-overlay {
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  display: flex;
  justify-content: center;
  background-color: #000000da;
}

.modal {
  text-align: center;
  background-color: white;
  color: black;
  height: 600px;
  width: 1000px;
  margin-top: 10%;
}

.close {
  color: black;
  cursor: pointer;
}

h6 {
  font-weight: 500;
  font-size: 28px;
  margin: 20px 0;
}

p {
  /* font-weight: 500; */
  font-size: 16px;
  margin: 20px 0;
}

button {
  background-color: #ac003e;
  width: 150px;
  height: 40px;
  font-size: 14px;
  border-radius: 16px;
  margin-top: 50px;
}
</style>
