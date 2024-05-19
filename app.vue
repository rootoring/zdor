<template>
  <div>
    <!-- <a target="_blank" class="bottom-btn" href="https://api.whatsapp.com/send/?phone=79280477768&text=%D0%97%D0%B4%D1%80%D0%B0%D0%B2%D1%81%D1%82%D0%B2%D1%83%D0%B9%D1%82%D0%B5%21+%D0%97%D0%B0%D0%BF%D0%B8%D1%88%D0%B8%D1%82%D0%B5+%D0%BC%D0%B5%D0%BD%D1%8F+%D0%BD%D0%B0+%D0%B1%D0%B5%D1%81%D0%BF%D0%BB%D0%B0%D1%82%D0%BD%D1%8B%D0%B9+%D0%BF%D1%80%D0%B8%D0%B5%D0%BC+%D0%BA+%D1%81%D0%BF%D0%B5%D1%86%D0%B8%D0%B0%D0%BB%D0%B8%D1%81%D1%82%D1%83++%D0%BF%D0%BE+%D0%BF%D1%80%D0%BE%D0%B3%D1%80%D0%B0%D0%BC%D0%BC%D0%B5+%22%D0%A1%D1%82%D1%80%D0%B0%D0%BD%D0%B0+%D0%97%D0%B4%D0%BE%D1%80%D0%BE%D0%B2%D1%8C%D1%8F%22.+&type=phone_number&app_absent=0">Записаться</a> -->
    <theHeader />
    <main>
      <TheBanner />
      <AboutUs />
      <Promotions />
      <Fillials />
      <Footer />
    </main>
  </div>
</template>
<script setup>
import Footer from "./components/footer.vue";
useHead({
  title:
    "Программа 'Страна Здоровья' Консультация специалиста бесплатно. Мы рядом ",
  link: [
    {
      rel: "icon",
      type: "image/x-icon",
      href: "https://klinika-zdorovie.ru/wp-content/uploads/2021/03/favicon-80x80-optimized.png",
    },
  ],
});
</script>
<style scoped>
.bottom-btn {
  position: fixed;
  bottom: 25px;
  right: 20px;
  background: #df0048;
  z-index: 99;
  padding: 10px 15px;
  border-radius: 8px;
  color: #fff;
  box-shadow: 0 0 0 0 rgba(223, 0, 72, 1);
  transform: scale(1);
  animation: pulse 2s infinite;
  letter-spacing: 2px;
}
a:visited {
  color: #fff;
}

@keyframes pulse {
  0% {
    transform: scale(0.98);
    box-shadow: 0 0 0 0 rgba(156, 2, 51, 0.7);
  }

  70% {
    transform: scale(1);
    box-shadow: 0 0 0 10px rgba(156, 2, 51, 0);
  }

  100% {
    transform: scale(0.98);
    box-shadow: 0 0 0 0 rgba(156, 2, 51, 0);
  }
}
</style>
