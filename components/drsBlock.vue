<template>
    <section class="drs-block">
        <div class="contaner">
            <h2 class="drs-block__title">В нашем центре для вас доступны следующие специалисты</h2>
            <div class="drs-block__cards">
                <div
                v-for="dr of drs"
                class="text-wrap drs-block__card pa-3"

            >{{ dr }}</div>
            </div>

            <p class="drs-block__desc description">Нажмите кнопку "Записаться"
                в сообщении укажите специалиста, и мы запишем вас на удобное время</p>
        </div>
    </section>
</template>
<script setup>
const props = defineProps({
  drs: {
    required: true,
  },
})
</script>
<style lang="scss">
.drs-block{
    margin-top: 80px;
    padding: 10px 15px;
    .drs-block__title{
        text-align: center;
        margin-bottom: 30px;
    }
    .drs-block__cards{
        display: grid;
        grid-template-columns: 1fr 1fr 1fr;
        gap: 20px;

        .drs-block__card{
            display: flex;
            align-items: center;
            justify-content: center;
            font-family: TTLakes;
            transition: .3s all;
            text-align: center;
            font-size: 20px ;
            color: #424563;
            border-radius: 8px;
            padding: 10px 15px;
            opacity: .8;
            &:hover{
                background-color:#DF0048 ;
                color: #fff;
            }   
        }
    }
    .drs-block__desc{
        margin-top: 90px;
        text-align: center;
        margin-bottom: 70px;
       
    }
}
@media(max-width:748px){ 
    .drs-block__cards{
        display: grid;
        grid-template-columns: 1fr 1fr !important;
    }
}
@media(max-width:570px){ 
    .drs-block__cards{
        display: grid;
        grid-template-columns: 1fr  !important;
    }
}
</style>