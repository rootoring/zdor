<template>
  <footer class="footer">
    <div class="footer-inner">
      <div class="footer-section">
        <img
          src="https://avatars.mds.yandex.net/get-maps-adv-crm/11387709/2a0000018cb57cb7800e869c47a78d68b4c7/landing_logo"
          alt="Логотип"
          class="footer-logo"
        />
      </div>
      <div class="footer-section">
        <h3>Контакты</h3>
        <a target="_blank" href="tel:+79280477768"
          ><v-icon class="tel-ico" icon="mdi-phone" /><span
            >+79280477768</span
          ></a
        >
      </div>
      <div class="footer-section">
        <h3>Навигация</h3>
        <ul class="footer-nav">
          <li><a href="#promotions">Акции</a></li>
          <li><a href="">Каталог</a></li>
          <li><a href="#contacts">Врачи</a></li>
        </ul>
      </div>
    </div>
    <div class="footer-bottom">
      <p>&copy; 2024 ООО «Медицинский центр «Здоровье» . Все права защищены.</p>
    </div>
  </footer>
</template>

<script setup></script>

<style scoped>
.footer {
  background-color: #ffffff;
  color: #333;
  padding: 40px 20px;
  text-align: center;
}

.footer-inner {
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
}

.footer-section {
  flex: 1;
  margin: 10px;
}

.footer-logo {
  max-width: 150px;
}

.footer h3 {
  font-size: 18px;
  margin-bottom: 15px;
}

.footer p,
.footer a {
  margin: 5px 0;
  color: #333;
  text-decoration: none;
}

.footer-nav {
  list-style: none;
  padding: 0;
}

.footer-nav li {
  margin: 5px 0;
}

.footer-nav a:hover {
  color: #ff4081;
}

.footer-bottom {
  margin-top: 20px;
  font-size: 14px;
  border-top: 1px solid #e0e0e0;
  padding-top: 10px;
}

@media (max-width: 768px) {
  .footer-inner {
    flex-direction: column;
  }
}
</style>
