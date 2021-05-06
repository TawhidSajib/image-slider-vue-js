<template>
  <div id="app">
    <Slider :images="images">
      <template scope="{imgData}">
        <div
          style="
            display: flex;
            align-items: flex-end;
            justify-content: center;
            height: 100%;
          "
        >
          <div>
            <h1 class="imageTitle">{{ imgData.title }}</h1>
          </div>
        </div>
      </template>
    </Slider>
  </div>
</template>

<script>
import Slider from "./components/Slider.vue";
import slider1 from "@/assets/images/slider1.jpg";
import slider2 from "@/assets/images/slider2.jpg";
import slider3 from "@/assets/images/slider3.jpg";
import slider4 from "@/assets/images/slider4.jpg";
export default {
  name: "App",
  components: {
    Slider,
  },
  data() {
    return {
      images: [
        { image: slider1, title: "Tanguar Haor" },
        { image: slider2, title: "Bogalake" },
        { image: slider3, title: "Saint Martin" },
        { image: slider4, title: "Nafakhum" },
      ],
    };
  },
};
</script>
<style>
@import "./assets/styles/style.css";
.imageTitle {
  color: white;
  margin-bottom: 30px;
}
</style>

