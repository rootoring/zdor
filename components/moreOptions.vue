<template>
  <section class="moreOptions">
    <div class="contaner">
      <h3 class="moreOptions__title">Так же в нашем центре есть</h3>
      <ul class="moreOptions__lists">
        <li class="moreOptions__list" v-for="option of options">
          <v-icon class="minus-ico" icon="mdi-minus" />
          <span v-html="option"></span>
        </li>
      </ul>
    </div>
  </section>
</template>
<script setup>
const props = defineProps({
  options: {
    required: true,
  },
});
</script>

<style lang="scss">
.list-opacity {
  opacity: 0.8;
}
.moreOptions {
  background-color: #fff;
  padding: 80px 15px;

  .moreOptions__title {
    text-align: center;
    font-size: 25px;
  }
  .moreOptions__lists {
    margin-top: 60px;
    display: flex;
    flex-direction: column;
    gap: 20px;

    .moreOptions__list {
      font-size: 17px;

      .minus-ico {
        opacity: 0.8;
      }
    }
  }
}
@media (max-width: 768px) {
  .moreOptions {
    padding: 40px 15px;
    .moreOptions__title {
      font-size: 22px;
    }
    .moreOptions__lists {
      gap: 15px;

      .moreOptions__list {
        font-size: 14px;
      }
    }
  }
}
</style>
