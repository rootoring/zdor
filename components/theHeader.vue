<template>
  <header>
    <div class="contaner">
      <div class="header-blocks font-ttlikes">
        <div class="header-block d-flex justify-space-between align-center">
          <div class="header-block__logo d-flex align-center">
            <nuxt-link to="/">
              <img
                class="logo"
                src="https://avatars.mds.yandex.net/get-maps-adv-crm/11387709/2a0000018cb57cb7800e869c47a78d68b4c7/landing_logo"
                alt="logo"
              />
            </nuxt-link>
            <a
              class="header-block__cont-tel"
              target="_blank"
              href="tel:+79280477768"
              ><v-icon class="tel-ico" icon="mdi-phone" /><span
                >+79280477768</span
              ></a
            >
          </div>
          <div
            class="d-flex flex-column align-end opacity-80 header-blocks__time"
          >
            <span>Пн - Пт с 8:30 до 18:00</span>
            <span>Сб с 9:00 до 16:00</span>
          </div>
          <button
            @click="
              ($event) => {
                $event.stopPropagation();
                showMenu = !showMenu;
              }
            "
            class="burger"
          >
            <v-icon class="menu-ico" icon="mdi-menu" />
          </button>
        </div>

        <div class="d-flex justify-space-between align-center">
          <nav>
            <ul>
              <li><a href="#promotions">Акции</a></li>
              <li><a href="">Каталог</a></li>
              <li><a href="#contacts">Врачи</a></li>
            </ul>
          </nav>
          <div class="head-btns">
            <a class="head-btn" href="#contacts">Записаться на прием</a>
            <a class="head-btn green-btn" href="#">Вызов врача на дом</a>
          </div>
        </div>
      </div>
    </div>
    <div
      :class="`menu  font-ttlikes ${showMenu ? 'menu-actv' : ''}`"
      ref="menu"
    >
      <button @click="showMenu = !showMenu" class="menu__close">
        <v-icon class="menu-ico" icon="mdi-close" />
      </button>
      <a href="#aboutUs">Акции</a>
      <a href="">Каталог</a>
      <a href="#contacts">Врачи</a>
    </div>
  </header>
</template>
<script setup>
let showMenu = ref(false);
let menu = ref();

onMounted(() => {
  document.addEventListener("click", (e) => {
    if (showMenu.value) {
      if (e.target !== menu.value) {
        showMenu.value = !showMenu.value;
      }
    }
  });
});
</script>
<style scoped lang="scss">
.header-block__cont-tel {
  transition: 0.3s all;
  font-size: 18px !important;
  &:hover {
    opacity: 0.7;
  }
}
.head-btns {
  display: flex;
  gap: 8px;
}
.green-btn {
  background: #09aea8 !important;
}
.head-btn {
  display: inline-block;
  padding: 12px 20px;
  background: #e30043;
  border-radius: 8px;
  font-weight: 800 !important;
  font-size: 14px;
  line-height: 18px;
  text-transform: uppercase;
  text-decoration: none;
  color: #ffffff !important;
  cursor: pointer;
  transition: all 0.2s ease;
  &:hover {
    opacity: 0.8;
  }
}

.tel-ico {
  color: #df0048;
}
.menu__close {
  position: absolute;
  top: 18px;
  left: 18px;
  font-size: 22px;
}
.burger {
  font-size: 26px;
  display: none;
}
.menu-actv {
  width: 70% !important;
  transform: translateX(0px) !important;
  -webkit-box-shadow: -14px 4px 22px -23px rgba(66, 68, 90, 1);
  -moz-box-shadow: -14px 4px 22px -23px rgba(66, 68, 90, 1);
  box-shadow: -14px 4px 22px -23px rgba(66, 68, 90, 1);
}
.menu {
  height: 100%;
  position: fixed;
  background-color: #fff;
  width: 0%;
  display: flex;
  top: 0;
  flex-direction: column;
  right: 0;
  justify-content: center;
  align-items: center;
  gap: 33px;
  padding: 10px;
  transition: 0.3s all;
  transform: translateX(300px);

  a {
    font-size: 20px;
    padding: 5px 20px;
    border-radius: 8px;
    transition: 0.3s all;
    font-family: TTLakes;
    width: 100%;
    text-align: center;
    &:hover {
      background-color: #df0048;
      color: #fff;
    }
  }
}
header {
  padding: 0px 10px 15px 10px;
  box-shadow: rgba(149, 157, 165, 0.2) 0px 8px 24px;
  position: sticky;
  top: 0;
  z-index: 999;
  background: #fff;
  .header-blocks {
    display: flex;
    gap: 15px;
    flex-direction: column;
    .logo {
      width: 80px;
    }
    nav {
      ul {
        display: flex;
        justify-content: space-between;

        li {
          a {
            font-size: 20px;
            padding: 5px 20px;
            border-radius: 8px;
            transition: 0.3s all;
            font-weight: 900;
            &:hover {
              background-color: #df0048;
              color: #fff;
            }
          }
        }
      }
    }
  }
}
@media (max-width: 768px) {
  .head-btn {
    padding: 10px 10px;
  }
  .header-blocks {
    gap: 6px !important;
  }
  .logo {
    width: 70px !important;
  }
  nav {
    display: none;
  }
  .place {
    width: auto !important;
    margin: 0 auto;
  }
  .burger {
    display: block;
  }
  .header-blocks__time {
    align-items: center !important;
  }
  .head-btns {
    margin: 0 auto;
  }
  .header-block__logo {
    .header-block__cont-tel {
      font-size: 16px !important;
      padding-left: 20px;
      span {
        display: none;
      }
    }
  }
}
</style>
