<template>
  <section class="fillials">
        <h2 class="fillials__title">Наши Клиники</h2>    
    <v-tabs
      v-model="tab"
      align-tabs="center"
      color="pink-lighten-1"
      class="py-0"
    >
      <v-tab 
       class="fillials__swipper-title"
      v-for="contact of contacts"
      :value="contact.id-1">{{ contact.title }}</v-tab>
    </v-tabs>

    <v-tabs-window v-model="tab">
      <v-tabs-window-item
        v-for="n in contacts"
        :key="contacts.id"
        :value="contacts.id"
      >
        <v-container fluid>
          <v-row class="lists">
            <DrsBlock :drs ="contacts[tab].drs"/>
            <MoreOptions :options="contacts[tab].options"/>
            <theContact :inf="contacts[tab]"/>
          </v-row>
        </v-container>
      </v-tabs-window-item>
    </v-tabs-window>

        <!-- <ul class="fillials__lists">
          <li 
          v-for="contact of contacts">
          <nuxt-link  class="fillials__list" :to="`fillials/${contact.id}`">
          <a class="list__title list__link" target="_blank" :href="contact.mapLink">{{ contact.title }}</a>
          <span class="list__blocks"><v-icon class="tel-ico" icon="mdi-phone" />Телефон: <a v-for="tel of contact.tel" class="list__link" target="_blank" :href="`tel:${tel}`">{{tel}}</a></span>
          <span class="list__blocks"><v-icon class="tel-ico" icon="mdi-email" />E-mail:<a class="list__link" target="_blank" :href="`mailto:${contact.mail}`">{{contact.mail}}</a></span>
          <span class="list__title">Время работы:</span>
          <span class="list__times">
            
            <span class="list__time" v-if="contact.pol">
              Поликлиника: <p class="list__time-desc" v-html="contact.pol"></p>
            </span>
            <span class="list__time" v-if="contact.mrt">
              МРТ, КТ: <p  class="list__time-desc" v-html="contact.mrt"></p>
            </span>
            <span class="list__time" v-if="contact.lab">
              Лаборатория: <p  class="list__time-desc" v-html="contact.lab"></p>
            </span>
            <span class="list__time" v-if="contact.timeWork">
              <p  class="list__time-desc" v-html="contact.timeWork"></p>
            </span>
          </span></nuxt-link>
          </li>
        </ul> -->
 
  </section>
</template> 
<script setup>
import { ref } from 'vue';
import contacts from '../mocks/contactsMocks.js'

let data = ref()

onMounted(() => {
 
});
let tab = ref()
</script>
<style lang="scss">
.fillials__swipper-title{
  font-family: "Montserrat", sans-serif !important;
}
.lists{
  display: flex;
  flex-direction: column;
}
.fillials{
  padding-top: 80px;

  .fillials__title{
    text-align: center;
    margin-bottom: 33px;
  }

  .fillials__lists{
    display: flex;
    gap: 18px;
    justify-content: center;
    align-items:stretch;

      li{ 
        width: 100%;
        cursor: pointer;
      }
    .fillials__list{
      height: 100%;
      box-shadow: rgba(149, 157, 165, 0.2) 0px 8px 24px;
      background-color: #ffffff;
      padding: 30px;
      border-radius: 8px;
      color: #000000;
      display: flex;
      flex-direction: column;
      transition: .3s ease-in-out;
      &:hover{
        box-shadow: rgba(149, 157, 165, 0.7) 0px 8px 24px;
        background-color: #DB004B;
        color: #ffffff;
        .list__link{
          color: #ffffff;
        }
      }
      .list__link{
        color: #000000;
        margin-left: 6px;
        transition: .3s all;
        &:hover{
          opacity: .3;
        }
      }
      .list__title{
        font-size: 20px;
        padding-bottom: 35px;
        margin: 0 auto;
      }
      .list__blocks{
        margin-bottom: 15px;
        font-size: 17px;
        .tel-ico{
          margin-right: 8px;
        }
      }
      .list__times{
        display: flex;
        justify-content: space-around;

        .list__time{
          display: flex;
          flex-direction: column;
          gap:17px;
          font-size: 18px;
          .list__time-desc{
            line-height: 25px;
            opacity: .7;
            font-size: 16px !important;
          }
        }
      }
    }
  }
}
@media(max-width:748px){ 
  .list__times{
    flex-direction: column;
    gap: 33px;
  }
}
@media(max-width:850px){ 
  .fillials__lists{
    flex-direction: column;
  }
}
</style>