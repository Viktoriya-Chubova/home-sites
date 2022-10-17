<template>
   <div class="cover">
      <div class="container">
         <div class="cover__content">
            <p class="cover__title">Комплексный интернет-маркетинг</p>
            <p class="cover__text">Мы помогаем бизнесу находить клиентов быстрее, интегрируя маркетинговые, обучающие и технологические продукты</p>
            <AppButton2 class="cover__btn">Заказать увеличение продаж</AppButton2>
            <AppButton2 variant="white">Заказать экспертный аудит</AppButton2>
         </div>
      </div>
   </div>
</template>

<script>
import AppButton2 from './AppButton2.vue';
   export default {
    components: { AppButton2 }
}
</script>

<style lang="scss" scoped>
@import "../assets/layouts/index.scss";

.cover {
   background: url('../assets/image/mainphoto.jpg') no-repeat center;
   background-size: cover;
   color: $white;
   padding: 170px 0 210px;
   &__content{
      max-width: 780px;
   }
   &__title {
      font-weight: 700;
      font-size: 68px;
      margin-bottom: 28px;
   }

   &__text {
      font-weight: 500;
      font-size: 16px;
      margin-bottom: 52px;
      line-height: 140%;
   }
   &__btn{
      margin-right: 32px;
   }
   
}
@media screen and (max-width: 991.98px){
   .cover {

      &__content {
      }

      &__title {
         font-size: 50px;
      }

      &__text {
      }

      &__btn {
      }
   }

}
@media screen and (max-width: 767.98px){
   .cover {
      background: url('../assets/image/mainphoto.jpg') no-repeat left;
      padding: 100px 0 150px;
      &__content {
      }

      &__title {
         font-size: 40px;
      }

      &__text {
         
      }

      &__btn {
         margin-bottom: 20px;
      }
      }

}
@media screen and (max-width: 479.98px){
   .cover {

      &__content {
      }

      &__title {
         font-size: 30px;
      }

      &__text {
      }

      &__btn {
      }
   }
}
</style>