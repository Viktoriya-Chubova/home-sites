<template>
   <div class="anticrisis">
      <div class="container">
         <p class="anticrisis__maintitle"><span>Антикризисные</span> DIGITAL-пакеты</p>
         <div class="anticrisis__cards">
            <div class="anticrisis__card" v-for="item in data" :key="item">
               <img class="anticrisis__image" :src="require(`../assets/image/${item.image}.png`)">               
               <div class="anticrisis__content">
                  <p class="anticrisis__title">{{item.title}}</p> <hr class="anticrisis__hr">
                  <p class="anticrisis__subtitle">{{item.subtitle}}</p><hr class="anticrisis__hr">
                  <p class="anticrisis__text">{{item.text}}</p>
                  <p class="anticrisis__discount">Специальная скидка до <span>{{item.discount}}</span> на каждую услугу в пакете</p>
                  <AppButton class="anticrisis__btn">Приобрести пакет</AppButton>
               </div>
            </div>
         </div>
      </div>

   </div>
</template>

<script>
import AppButton from './AppButton.vue';
   export default {
    name: "anticrisis",
    props: {
        data: {
            type: Array,
            default: () => []
        }
    },
    components: { AppButton }
}
</script>

<style lang="scss" scoped>
@import "../assets/layouts/index.scss";

.anticrisis {
   padding: 120px 0;

   &__maintitle {
      font-weight: 700;
      font-size: 38px;
      margin-bottom: 60px;
      & span{
         color: $orange;
      }
   }

   &__cards {
      display: flex;
      justify-content: space-between;
      justify-content: center;
      flex-wrap: wrap;
      align-content: center;
      font-weight: 500;
      gap: 60px;
      @media screen and (max-width: 1280px){
         gap: 20px;
      }
   }

   &__card {
      max-width: 360px;
      position: relative;
      color: $white;
      line-height: 140%;
      
   }
   &__image{
      
   }
   &__content{
      position: absolute;
      top: 0;
      padding: 40px 32px;
   }
   &__hr{
      margin-bottom: 20px;
      opacity: 0.2;
   }
   &__title {
      font-weight: 700;
      font-size: 18px;
      text-transform: uppercase;
      margin-bottom: 28px;
   }

   &__subtitle {
      margin-bottom: 20px;
   }

   &__text {
      margin-bottom: 28px;
      font-size: 14px;
      opacity: 0.5;
      
   }

   &__discount {
      margin-bottom: 36px;
      & span{
         font-weight: 800;
         font-size: 18px;
      }
   }
   &__btn{
      width: 296px;
   }
}
@media screen and (max-width: 767.98px){
   .anticrisis {
      padding: 80px 0;
      &__maintitle {
         font-size: 30px;
      }

   }
}
@media screen and (max-width: 479.98px){
   .anticrisis {
      padding: 80px 0;
      &__maintitle {
         font-size: 26px;
         margin-bottom: 30px;
      }


      &__image {
         width: 295px; 
      }

      &__content {
         padding: 30px 20px;
      }

      &__hr{
         margin-bottom: 15px;
      }
      &__title {
         font-weight: 600;
         font-size: 16px;      
         margin-bottom: 15px;
      }

      &__subtitle {
         font-size: 14px;
         margin-bottom: 15px;
      }

      &__text {
         margin-bottom: 15px;
         font-size: 12px;      
      }

      &__discount {
         margin-bottom: 20px;
         font-size: 12px;
         & span{         
            font-size: 14px;
         }
      }
      &__btn {
         width: 200px;
         height: 40px;
      }
   }
}
</style>