<template>
  <section id="promotions" class="prom">
    <h2 class="prom__title">Акции</h2>

    <v-container>
      <v-carousel v-model="currentSlide" hide-delimiters>
        <v-carousel-item v-for="(item, i) in items" :key="i">
          <v-sheet
            class="d-flex align-center justify-center"
            style="width: 100vw; background-color: #f8f8f8"
          >
            <img
              src="https://avatars.mds.yandex.net/get-maps-adv-crm/11387709/2a0000018e80cd47cc24d735634865d4cb9e/landing_background"
              alt="Slide Image"
              style="max-width: 100%; max-height: 100%"
            />
          </v-sheet>
        </v-carousel-item>
      </v-carousel>
      <v-row class="mt-2 align-center justify-center">
        <v-col cols="auto" v-for="(item, i) in items" :key="i">
          <v-btn
            icon
            :class="{
              'active-dot': i === currentSlide,
              'inactive-dot': i !== currentSlide,
            }"
            @click="currentSlide = i"
          >
            <v-icon>{{
              i === currentSlide
                ? "mdi-checkbox-blank-circle"
                : "mdi-checkbox-blank-circle-outline"
            }}</v-icon>
          </v-btn>
        </v-col>
      </v-row>
    </v-container>
  </section>
</template>
<script setup>
import { ref } from "vue";

const items = ref(["slide1.jpg", "slide2.jpg", "slide3.jpg", "slide4.jpg"]);
const currentSlide = ref(0);
const slideInterval = 5000;

const nextSlide = () => {
  currentSlide.value = (currentSlide.value + 1) % items.value.length;
};

let interval = null;

onMounted(() => {
  interval = setInterval(nextSlide, slideInterval);
});

onUnmounted(() => {
  clearInterval(interval);
});
</script>
<style lang="scss">
img {
  width: 100%;
  height: 100% !important;
}
.prom {
  scroll-margin-top: 80px;
  background-color: #fff;
  padding: 10px 15px;
  padding-bottom: 80px;
  .prom__title {
    text-align: center;
    margin-bottom: 20px;
  }
}
.active-dot {
  color: #e30043 !important;
}
.inactive-dot {
  color: #bdbdbd !important; /* Цвет: светло-серый */
}
.v-carousel {
  width: 100vw;
  height: 600px !important;
}
.v-carousel-item {
  width: 100vw;
  display: flex;
  justify-content: center;
  align-items: center;
}
.v-responsive__content {
  display: flex;
  align-items: center;
}
@media (max-width: 768px) {
  .v-window__left,
  .v-window__right {
    display: none !important;
  }
}
</style>
