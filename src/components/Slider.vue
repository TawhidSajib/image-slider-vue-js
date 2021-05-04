
<template>
  <div class="container">
    <div class="item">
      <img class="image" :src="currentImg.image" />
      <div class="left-slide" @click="prev">
        {{ prevIcon }}
      </div>
      <div class="right-slide" @click="next">
        {{ nextIcon }}
      </div>
      <p class="imageTitle">{{ currentImg.title }}</p>
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
      images: [
        { image: slider1, title: "Tanguar Haor" },
        { image: slider2, title: "Bogalake" },
        { image: slider3, title: "Saint Martin" },
        { image: slider4, title: "Nafakhum" },
      ],
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
