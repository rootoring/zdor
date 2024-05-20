<template>
  <section id="promotions" class="prom">
    <h2 class="prom__title">Акции</h2>

    <v-container class="prom-contaner">
      <v-carousel v-model="currentSlide" hide-delimiters>
        <v-carousel-item v-for="(item, i) in items" :key="i">
          <v-sheet
            class="swdfwd d-flex align-center justify-center"
            style="width: 100vw; background-color: #f8f8f8"
          >
            <img
              src="https://klinika-zdorovie.ru/wp-content/uploads/2024/02/stop-virus-3-scaled-optimized.jpg"
              alt="Slide Image"
              style="max-width: 100%; max-height: 100%"
            />
          </v-sheet>
        </v-carousel-item>
      </v-carousel>
      <v-row class="my-row mt-2 align-center justify-center">
        <v-col cols="auto" v-for="(item, i) in items" :key="i">
          <v-btn
            icon
            class="btn-dot"
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
.prom-contaner {
  max-width: 100% !important;
}
.my-row {
  margin: 20px 0 0 0 !important;
}
.btn-dot {
  max-width: 20px !important;
  max-height: 20px !important;
}
img {
  width: 100%;
  height: 100% !important;
}
.prom {
  scroll-margin-top: 80px;
  background-color: #fff;
  padding-bottom: 60px;
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
  height: auto !important;
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
.v-window__left,
.v-window__right {
  color: transparent;
  transition: color 0.3s;
}
.v-window__left:hover,
.v-window__right:hover {
  color: #e30043 !important; /* Цвет: розовый */
}
@media (max-width: 768px) {
  .v-window__left,
  .v-window__right {
    display: none !important;
  }
}
</style>
