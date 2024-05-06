<template>
<section id="promotions" class="prom">
  <div class="contaner">
  <h2 class="prom__title">Акции</h2>

    <v-slide-group
      class="pa-2"
      show-arrows
    >
      <v-slide-group-item
        v-for="n in 15"
        :key="n"

      >
        <v-card
          class="ma-3"
          color="grey-lighten"
          height="200"
          width="250"
        >
          <div class="d-flex fill-height align-center justify-center">
            <img class="banner__img" src="https://avatars.mds.yandex.net/get-maps-adv-crm/11387709/2a0000018e80cd47cc24d735634865d4cb9e/landing_background" alt="Banner">
          </div>
        </v-card>
      </v-slide-group-item>
    </v-slide-group>

</div>
</section>
</template>
<script setup>

</script>
<style lang="scss">
.prom{
  scroll-margin-top: 80px;
  background-color: #fff;
  padding: 10px 15px;
  padding-bottom: 80px;
  .prom__title{
    text-align: center;
    margin-bottom: 20px;
  }
}</style>