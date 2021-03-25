<template>
  <div>
    <img
      class="asia"
      v-if="!isVisible"
      @click="changeVisibility"
      src="/img/111.jpg"
    />
  </div>
  <div v-if="isVisible">
    <iframe
      class="video"
      src="https://www.youtube.com/embed/_z-1fTlSDF0?start=3&autoplay=1"
      title="YouTube video player"
      frameborder="0"
      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
      allowfullscreen
    ></iframe>
    <br />

    <img :src="path" alt="DEEP" />

    <br />
    <div class="flew">
      <button @click="prevPhoto">Previous</button>
      <hello-world></hello-world>
      <button @click="nextPhoto">Next</button>
    </div>
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
      isVisible: false,
      maxNoOfPhoto: 13,
      photoNumber: 1,
    };
  },
  methods: {
    nextPhoto() {
      if (this.photoNumber == this.maxNoOfPhoto) this.photoNumber = 0;
      this.photoNumber++;
    },
    changeVisibility() {
      this.isVisible = !this.isVisible;
    },
    prevPhoto() {
      if (this.photoNumber == 1) this.photoNumber = this.maxNoOfPhoto + 1;
      this.photoNumber--;
    },
  },
};
</script>

<style>
body {
  margin: 0;
}

.asia {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
.video {
  width: 0;
  height: 0;
  margin: 0;
}

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
