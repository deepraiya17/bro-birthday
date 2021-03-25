<template>
  <div v-if="isVisible" class="textfree">{{ msgA }}</div>
  <div>
    <img
      class="asia"
      v-if="!isVisible"
      @click="changeVisibility"
      src="/img/111.jpg"
    />
  </div>
  <div v-if="isVisible">
    <video width="320" height="100" controls autoplay>
      <source src="/video/1.mp4" type="video/mp4" />
    </video>
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
    msgA() {
      return this.message.substring(0, this.photoNumber);
    },
  },
  data() {
    return {
      isVisible: false,
      maxNoOfPhoto: 30,
      photoNumber: 1,
      message: "Happy Birthday To Biig Brother",
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

      setTimeout(this.carousal, 3000);
    },
  },
};
</script>

<style>
body {
  margin: 0;
}

.textfree {
  text-align: center;
  color: blue;
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
