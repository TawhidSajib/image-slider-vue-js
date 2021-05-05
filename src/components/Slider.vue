
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
export default {
  data() {
    return {
      prevIcon: "<",
      nextIcon: ">",
      index: 0,
    };
  },
  props: {
    images: {
      type: Array,
    },
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
