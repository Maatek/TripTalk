<template>
  <div class="home">
    <div class="image-container">
      <img alt="Vue logo" src="https://www.itc-travel.hr/wp-content/uploads/2016/01/2individualna-1200x478.jpg" class="fullscreen-image">
      <h1 class="image-text"><b>Welcome to TripTalk</b></h1>
    </div>
  </div>
</template>

<style>
.home {
  display: flex;
  justify-content: center;
  align-items: center;
}

.image-container {
  position: relative;
}

.fullscreen-image {
  width: 100%;
  height: 100vh;
  object-fit: cover;
}

.image-text {
  position: absolute;
  top: 25%;
  left: 75%;
  transform: translate(-50%, -50%);
  color: black;
  font-size: 80px;
  font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
  font-weight: 100;
}
</style>

<script>
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'HomeView',
  components: {
    HelloWorld
  }
}
</script>
