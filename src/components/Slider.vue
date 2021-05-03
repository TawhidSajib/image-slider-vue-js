<template>
  <div class="container">
    <div class="item">
      <img class="image" :src="firstImage" />
      <button class="left-slide" @click="prev" :disabled="index === 0">
        {{ prevIcon }}
      </button>
      <button
        class="right-slide"
        @click="next"
        :disabled="index === this.images.length - 1"
      >
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
      firstImage: slider1,
      images: [slider1, slider2, slider3, slider4],
      index: 0,
    };
  },
  methods: {
    next() {
      this.index++;
      this.firstImage = this.images[this.index];
    },
    prev() {
      this.index--;
      this.firstImage = this.images[this.index];
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
.container {
  max-width: 1170px;
  margin: 0 auto;
  text-align: center;
}
.item {
  position: relative;
  border: 10px solid blue;
}
.image {
  max-width: 100%;
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