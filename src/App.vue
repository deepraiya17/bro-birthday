<template>
  <img src="./assets/IMG_0075.jpg" alt="bro" />
  <br />
  <hello-world></hello-world>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
export default {
  components: { HelloWorld },
};
</script>

<style>
img {
  height: 540px;
  /* margin: 100px; */
  width: 80%;
}
</style>
