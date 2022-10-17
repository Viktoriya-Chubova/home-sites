<template>
   <div class="footer">
      <div class="container">
         <div class="footer__content">
            <div class="footer__info">
               <div>
                  <img class="footer__logo" src="../assets/image/logoFooter.png" alt="logo">
                  <p class="footer__region">Ваш регион: <span>Тула</span></p>
               </div>
               <div>
                  <div class="footer__contacts">
                     <a class="footer__phone" href="tel:+74952236659">+7 (495) 223-66-59</a> 
                     <p>г. Тула, ул. Пушкинская, 27</p>
                  </div>
                  <div class="footer__inn">
                     <p >ИНН 123456789</p>
                     <p >ОГРН 123456789010</p>
                  </div>   
                  <div class="footer__icons">
                     <img src="../assets/image/icons/vk.svg" alt="">
                     <img src="../assets/image/icons/telegram.svg" alt="">
                  </div>               
               </div>
               
            </div>
            <div class="footer__cards">
               <div class="footer__card" v-for="card in data" :key="card">
                  <div class="footer__name">{{card.name}}</div>
                  <ul class="footer__list" >
                     <li class="footer__item" v-for="item in card.menu" :key="item">
                        <router-link  href="" :to="item.path">{{item.name}}</router-link>                          
                     </li> 
                  </ul> 
               </div>
            </div>
         </div>
         <div class="footer__foot">
            <p>© 2008-2022 Компания «ДОМ САЙТОВ»</p>
            <div class="footer__links-foot">
               <a href="">Карта сайта</a> | <a href="">Политика конфиденциальности</a>
            </div>
         </div>
      </div>
   </div>
</template>

<script>
   export default {
      name: 'footer',
      props: {
         data: {
            type: Array,
            default: ()=> []
         }
      }
   }
</script>

<style lang="scss" scoped>
@import "../assets/layouts/index.scss";

.footer {
   background: $grey;
   padding-top: 100px;
   font-size: 14px;
   font-weight: 500;
   color: $white;
   &__content {      
      display: flex;
      justify-content: space-between;
   }

   &__info {
      
   }
   &__logo{
      margin-bottom: 57px;
   }
   &__region {
      margin-bottom: 20px;
      color: rgba($white, 0.2);
      & span{
         text-decoration: underline;
         color: rgba($white, 1);
      }
   }

   &__contacts {
      margin-bottom: 12px;
      line-height: 170%;
   }

   &__phone {
      text-decoration: none;
   }

   &__inn {
      margin-bottom: 28px;
      opacity: 0.5;
      line-height: 170%;
   }

   &__icons {
      display: flex;
      gap: 20px;
   }

   &__cards {
      display: flex;
      justify-content: space-between;
      gap: 107px;
      
   }

   &__card {
      width: 228px;
   }

   &__name {
      color: rgba($white, 0.5);
      margin-bottom: 24px;
   }

   &__list {
      list-style-type: none;
      margin: 0;
      padding: 0;
      margin-bottom: 80px;
   }

   &__item {      
      
      line-height: 170%;
   }

   &__foot {
      display: flex;
      justify-content: space-between;
      color: rgba($white, 0.5);
      padding: 20px 0 16px;
      border-top: 1px solid rgba($white, 0.1);
      font-size: 12px;
   }

   &__links-foot {
      a {             
         color: rgba($white, 0.5);    
         &:hover {
            color: rgba($white, 1);
         }    
      }

   }
}


a {      
   text-decoration: none;
   color: $white;
   &:hover {
      color: rgba($white, 0.5);
   }
   &:active{
      color: rgba($white, 0.2);      
   }
}

@media screen and (max-width: 1280px){
   .footer{
      &__cards{
         gap: 50px;
      }
   }
}
@media screen and (max-width: 1087px){
   .footer {
      padding-top: 70px;
      &__content {
         flex-direction: column;
      }

      &__info {
         display: flex;
         justify-content: space-between;
         margin-bottom: 60px;
      }     

      &__cards {
         flex-wrap: wrap;
         gap: 30px;
         margin-bottom: 30px;
      }


      &__list {
         margin-bottom: 0px;
         
      }

      
   }
}
@media screen and (max-width: 479.98px){
   .footer {
      padding-top: 70px;
      

      &__info {
         flex-direction: column;
         margin-bottom: 40px;
         align-items: center;
         text-align: center;
      }     
      &__icons {
         justify-content:  center;
      }
      &__logo{
         margin-bottom: 35px;
      }
      


      
      &__foot{
         flex-direction: column;
         gap: 10px;
         font-size: 11px;
      }
      
   }
}
</style>