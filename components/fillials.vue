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
        @click="addQueryParam(contact.id - 1)"
        class="fillials__swipper-title font-ttlikes"
        v-for="contact of contacts"
        :value="contact.id - 1"
        >{{ contact.title }}</v-tab
      >
    </v-tabs>

    <v-tabs-window v-model="tab">
      <v-tabs-window-item
        v-for="n in contacts"
        :key="contacts.id"
        :value="contacts.id"
      >
        <v-container fluid>
          <v-row class="lists">
            <DrsBlock :drs="contacts[tab].drs" />
            <MoreOptions :options="contacts[tab].options" />
            <theContact :inf="contacts[tab]" />
          </v-row>
        </v-container>
      </v-tabs-window-item>
    </v-tabs-window>
    <div id="contacts"></div>
  </section>
</template>
<script setup>
import { ref } from "vue";
import contacts from "../mocks/contactsMocks.js";

const router = useRouter();
const route = useRoute();
let tab = ref();
const addQueryParam = (i) => {
  router.push({
    query: {
      fillial: i,
    },
  });
};
onMounted(() => {
  if (!route.query.fillial) return (tab.value = 0);
  tab.value = route.query.fillial;
});
</script>
<style lang="scss">
.fillials__swipper-title {
  font-family: "Montserrat", sans-serif !important;
}
.lists {
  display: flex;
  flex-direction: column;
}
.fillials {
  padding-top: 80px;

  .fillials__title {
    text-align: center;
    margin-bottom: 33px;
  }

  .fillials__lists {
    display: flex;
    gap: 18px;
    justify-content: center;
    align-items: stretch;

    li {
      width: 100%;
      cursor: pointer;
    }
    .fillials__list {
      height: 100%;
      box-shadow: rgba(149, 157, 165, 0.2) 0px 8px 24px;
      background-color: #ffffff;
      padding: 30px;
      border-radius: 8px;
      color: #000000;
      display: flex;
      flex-direction: column;
      transition: 0.3s ease-in-out;
      &:hover {
        box-shadow: rgba(149, 157, 165, 0.7) 0px 8px 24px;
        background-color: #db004b;
        color: #ffffff;
        .list__link {
          color: #ffffff;
        }
      }
      .list__link {
        color: #000000;
        margin-left: 6px;
        transition: 0.3s all;
        &:hover {
          opacity: 0.3;
        }
      }
      .list__title {
        font-size: 20px;
        padding-bottom: 35px;
        margin: 0 auto;
      }
      .list__blocks {
        margin-bottom: 15px;
        font-size: 17px;
        .tel-ico {
          margin-right: 8px;
        }
      }
      .list__times {
        display: flex;
        justify-content: space-around;

        .list__time {
          display: flex;
          flex-direction: column;
          gap: 17px;
          font-size: 18px;
          .list__time-desc {
            line-height: 25px;
            opacity: 0.7;
            font-size: 16px !important;
          }
        }
      }
    }
  }
}
@media (max-width: 748px) {
  .list__times {
    flex-direction: column;
    gap: 33px;
  }
}
@media (max-width: 850px) {
  .fillials__lists {
    flex-direction: column;
  }
}
</style>
