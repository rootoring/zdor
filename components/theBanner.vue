<template>
  <section class="banner">
    <div class="contaner">
      <h1>Программа "Страна Здоровья"</h1>
      <img
        class="banner__img"
        src="https://avatars.mds.yandex.net/get-maps-adv-crm/11387709/2a0000018e80cd47cc24d735634865d4cb9e/landing_background"
        alt="Banner"
      />
    </div>
  </section>
</template>
<style lang="scss">
.banner {
  padding-top: 20px;
  background-color: #fff;
  .banner__img {
    width: 100%;
    border-radius: 5px;
  }
}
@media (max-width: 768px) {
  .banner {
    padding-top: 10px;
    .banner__img {
      border-radius: 0px;
    }
  }
}
</style>
