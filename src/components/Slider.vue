<template>
  <div class="container">
    <button @click="prev">Previous</button>
    <img :src="firstImage" style="width: 800px; max-height: 500px" />
    <button @click="next">Next</button>
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
  box-sizing: 0;
  margin: 0;
  padding: 0;
}
.container {
  max-width: 1170px;
  margin: 0 auto;
  text-align: center;
}
</style>