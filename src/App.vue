<template>
  <embed />
  <img :src="path" alt="DEEP" />
  <br />
  <div class="flew">
    <button @click="prevPhoto">Previous</button>
    <hello-world></hello-world>
    <button @click="nextPhoto">Next</button>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
export default {
  components: { HelloWorld },
  computed: {
    path() {
      return `/img/${this.photoNumber}.jpeg`;
    },
  },
  data() {
    return {
      maxNoOfPhoto: 14,
      photoNumber: 1,
    };
  },
  methods: {
    nextPhoto() {
      if (this.photoNumber == this.maxNoOfPhoto) this.photoNumber = 0;
      this.photoNumber++;
    },
    prevPhoto() {
      if (this.photoNumber == 1) this.photoNumber = this.maxNoOfPhoto + 1;
      this.photoNumber--;
    },
  },
};
</script>

<style>
.flew {
  display: flex;
  justify-content: space-between;
}

img {
  height: 540px;
  /* margin: 100px; */
  /* width: 80%; */
}
</style>
