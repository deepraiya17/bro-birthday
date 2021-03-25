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
  </div>
</template>

<script>
export default {
  computed: {
    path() {
      return `/img/${this.photoNumber}.jpeg`;
    },
  },
  data() {
    return {
      isVisible: false,
      maxNoOfPhoto: 13,
      photoNumber: 0,
    };
  },
  methods: {
    changeVisibility() {
      this.isVisible = !this.isVisible;
      this.carousal();
    },
    carousal() {
      if (this.photoNumber === this.maxNoOfPhoto) this.photoNumber = 0;
      this.photoNumber++;

      setTimeout(this.carousal, 2000);
    },
  },
};
</script>

<style>
body {
  margin: 0;
}

img {
  display: block;
  margin-left: auto;
  margin-right: auto;
  height: 513px;
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
</style>
