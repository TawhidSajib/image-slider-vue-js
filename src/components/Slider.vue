<template>
  <div class="container">
    <div class="item">
      <img class="image" :src="currentImg" />
      <button class="left-slide" @click="prev">
        {{ prevIcon }}
      </button>
      <button class="right-slide" @click="next">
        {{ nextIcon }}
      </button>
    </div>
  </div>
</template>
<script>
import slider1 from "@/assets/images/slider1.jpg";
import slider2 from "@/assets/images/slider2.jpg";
import slider3 from "@/assets/images/slider3.jpg";
import slider4 from "@/assets/images/slider4.jpg";
export default {
  data() {
    return {
      prevIcon: "<",
      nextIcon: ">",
      images: [slider1, slider2, slider3, slider4],
      index: 0,
    };
  },
  computed: {
    currentImg() {
      return this.images[Math.abs(this.index) % this.images.length];
    },
  },
  methods: {
    next() {
      this.index++;
    },
    prev() {
      if (this.index === 0) {
        this.index = this.images.length - 1;
      } else {
        this.index--;
      }
    },
  },
};
</script>
<style>
* {
  margin: 0;
  padding: 0;
}
body {
  background-color: grey;
}
.item {
  position: relative;
  border: 10px solid blue;
  overflow: hidden;
  width: 700px;
  height: 400px;
  margin: 0 auto;
  top: 60px;
}
.image {
  width: 700px;
  height: 400px;
}
.left-slide,
.right-slide {
  position: absolute;
  height: 40px;
  width: 40px;
  background-color: #444444;
  border-radius: 50%;
  color: #ffffff;
  font-size: 20px;
  top: 50%;
  cursor: pointer;
  margin-top: -20px;
  text-align: center;
  line-height: 40px;
}
.left-slide:hover {
  background-color: blue;
  color: white;
}
.right-slide:hover {
  background-color: blue;
  color: white;
}
.container .left-slide {
  left: 30px;
}
.container .right-slide {
  right: 30px;
}
</style>