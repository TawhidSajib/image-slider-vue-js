
<template>
  <div class="container">
    <div class="item">
      <img class="image" :src="currentImg.image" />
      <div class="imageItem">
        <slot :imgData="currentImg"></slot>
        <div class="left-slide" v-if="showArrow" @click="prev">
          {{ prevIcon }}
        </div>
        <div class="right-slide" v-if="showArrow" @click="next">
          {{ nextIcon }}
        </div>
      </div>
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
      timer: null,
    };
  },
  props: {
    images: {
      type: Array,
    },
    autoPlay: {
      type: Boolean,
      default: false,
    },
    showArrow: {
      type: Boolean,
      default: true,
    },
  },
  mounted() {
    if (this.autoPlay) {
      this.startSlide();
    }
  },
  computed: {
    currentImg() {
      return this.images[Math.abs(this.index) % this.images.length];
    },
  },
  methods: {
    startSlide() {
      this.playing = true;
      this.timer = setInterval(this.next, 4000);
    },
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
