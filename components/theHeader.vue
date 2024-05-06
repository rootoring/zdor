<template>
  <header>
    <div class="contaner">
      <div class="header-block">
        <nuxt-link to="/">
          <img class="logo" src="https://avatars.mds.yandex.net/get-maps-adv-crm/11387709/2a0000018cb57cb7800e869c47a78d68b4c7/landing_logo" alt="logo">
        </nuxt-link>
      <nav>
        <ul>
          <li><a href="#promotions">Акции</a></li>
          <li><a href="">Каталог</a></li>
          <li><a href="#contacts">Контакты</a></li>
        </ul>
      </nav>
      <button @click="($event) =>{
        $event.stopPropagation()
        showMenu=!showMenu
      }" 
      class="burger"><v-icon class="menu-ico" icon="mdi-menu" /></button>
    </div>
    </div>
    <div 
    :class="`menu ${showMenu ? 'menu-actv' : '' }`"
    ref="menu" >
    <button @click="showMenu=!showMenu" class="menu__close"><v-icon class="menu-ico" icon="mdi-close" /></button>
      <a href="#aboutUs">О нас</a>
      <a href="">Каталог</a>
      <a href="#contacts">Контакты</a>
    </div>
  </header>
</template>
<script setup>
let showMenu = ref(false)
let menu = ref()

onMounted(() => {
  document.addEventListener('click',(e)=>{
    if(showMenu.value){
      if (e.target !== menu.value) {
        showMenu.value=!showMenu.value
      }
    }
  })
    });

</script>
<style scoped lang="scss">
.menu__close{
  position: absolute;
  top: 18px;
  left: 18px;
  font-size: 22px;
}
.burger{
  font-size: 26px;
  display: none;
}
.menu-actv{
  width: 70% !important;
  transform: translateX(0px) !important;
  -webkit-box-shadow: -14px 4px 22px -23px rgba(66, 68, 90, 1);
-moz-box-shadow: -14px 4px 22px -23px rgba(66, 68, 90, 1);
box-shadow: -14px 4px 22px -23px rgba(66, 68, 90, 1);

}
.menu{
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
  transition: .3s all;
  transform: translateX(300px);

  a{
    font-size: 20px;
    padding:5px 20px ;
    border-radius: 8px;
    transition: .3s all;
    font-family: TTLakes;
    width: 100%;
    text-align: center;
    &:hover{
      background-color:#DF0048 ;
      color: #fff;
    }
  }  
}
header{
  padding:0px 10px;
  box-shadow: rgba(149, 157, 165, 0.2) 0px 8px 24px;
  position: sticky;
  top: 0;
  z-index: 999;
  background: #fff;
  .header-block{
    display: flex;
    align-items: center;
    gap:8px;
    justify-content: space-between;
    .logo{
      width: 80px;
    }
    nav{
    
  
      ul{
        display: flex;
        justify-content: space-between;
     
        li{
          a{
            font-size: 20px;
            padding:5px 20px ;
            border-radius: 8px;
            transition: .3s all;
            font-family: TTLakes;
            &:hover{
              background-color:#DF0048 ;
              color: #fff;
            }
          }
        }
      }
    }
  }
}
@media(max-width:768px){ 
  nav{
    display: none;
  }
  .place{
    width: auto !important;
    margin: 0 auto;
  }
  .burger{
    display: block;
  }
}
</style>