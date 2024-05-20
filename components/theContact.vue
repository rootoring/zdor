<template>
  <section id="contacts" class="contact">
    <div class="contact__block map" v-html="inf.map"></div>
    <div class="contact__block contact__block-right">
      <h3>Контакты</h3>
      <a target="_blank" :href="inf.mapLink">
        <v-icon class="tel-ico" icon="mdi-map" />{{ inf.title }}</a
      >
      <a class="contact__block-tel" target="_blank" :href="`tel:${inf.tel}`"
        ><v-icon class="tel-ico" icon="mdi-phone" />{{ inf.tel }}</a
      >
      <a target="_blank" class="contact__block-tel" :href="inf.whatsapp"
        ><v-icon class="tel-ico" icon="mdi-whatsapp" />Записаться</a
      >
    </div>
  </section>
</template>
<script setup>
const props = defineProps({
  inf: {
    required: true,
  },
});
</script>
<style lang="scss">
.contact {
  scroll-margin-top: 70px;
  display: flex;
  .contact__block {
    width: 50%;
  }
  .contact__block-right {
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 15px;
    background-color: #df0048;
    color: #fff;
    gap: 20px;

    h3 {
      font-size: 28px;
      letter-spacing: 4px;
      font-weight: bolder;
    }
    a,
    a:visited {
      color: #fff;
      font-weight: 100;
    }

    .contact__block-tel {
      font-size: 18px;
      margin-top: 10px;
      letter-spacing: 1px;
      display: flex;
      align-items: center;
      gap: 5px;

      .tel-ico {
        font-size: 18px;
      }
    }
  }
}
@media (max-width: 748px) {
  .contact {
    flex-direction: column;
    .contact__block {
      width: 100%;
    }
    .map {
      iframe {
        height: 250px !important;
      }
    }
  }
  .contact__block-right {
    padding: 25px !important;
  }
}
</style>
