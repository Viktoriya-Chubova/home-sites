<template>
   <div class="header">            
      <div class="container">          
         <div class="header__content">
            <div class="header__up">
               <div class="header__logo">
                  <a href="/"><img src="../assets/image/logo.png" alt=""></a>
               </div>
               <p class="header__title">Увеличиваем продажи в Вашем бизнесе!</p>
               <div class="header__contacts">
                  <a class="header__phone" href="tel:+74872792910">+7 (4872) 79-29-10</a>               
                  <AppButton>
                     <img class="header__iconPhone" src="../assets/image/icons/phone.svg" alt="">
                     Заказать звонок
                  </AppButton>
               </div>
               <BurgerHeader :data="HeaderData"></BurgerHeader> 
            </div>
            
         </div>
      </div>
      <div class="header__down">
         <div class="container">
            <ul class="header__list"  >
               <li class="header__item" v-for="item in data" :key="item.id" >                  
                  <router-link  href="" :to="item.path" @click=toggle(item.dropdown) >{{item.name}}                     
                     <img class="header__dropdown" v-if="item.dropdown" src="../assets/image/icons/dropdown.png" alt="">
                     <div class="header__children-wrapper" v-if="item.dropdown">
                        <ul class="header__children"  v-show="show">
                           <li class="header__children-item"   v-for="index in item.dropdown" :key="index.id">
                              <div class="header__children-link"><router-link  href="" :to="index.path" @click="show===false" >{{index.name}}</router-link></div>
                              <p class="header__children-hit">{{index.hit}}</p>
                           </li>                           
                        </ul>
                     </div>
                  </router-link> 
               </li> 
               <a href="#"><img src="../assets/image/icons/search.svg" alt=""></a>
            </ul> 
         </div>  
      </div>
      
         
   </div>  
</template>

<script>
import {HeaderData} from '@/data/data.dummy'
import AppButton from './AppButton.vue';
import BurgerHeader from './BurgerHeader.vue';
   export default {
    name: "Header",
    props: {
        data: {
            type: Array,
            default: () => [], //возвращает пустой массив
        },
    },
    components: { AppButton, BurgerHeader },
    data() {
        return {
            show: false,            
            HeaderData:HeaderData,
        };
    },
    
    methods: {
      toggle(isDropdown) { 
         if(isDropdown){
            this.show = !this.show    
         }        
            
      },      
    }
    
}
</script>

<style lang="scss" scoped>
@import "../assets/layouts/index.scss";
.header {
   color: $typography;
   font-size: 14px;
   
   @media screen and (max-width: 767.98px){
      border: 1px solid rgba(51, 51, 51, 0.1);
      }
   &__content{
      @media screen and (max-width: 1086.98px){
         display: flex;
         align-items: center;
         justify-content: space-between;
         
      }
   }
   &__up {
      display: flex;
      width: 100%;
      align-items: center;
      margin: 26px 0;
      @media screen and (max-width: 767.98px){
         margin: 15px 0;
   
      
      
      }
   }

   &__logo {
      min-width:45px;
      @media screen and (max-width: 767.98px){
         position: relative;
         overflow:hidden;
         width:45px;
         
      }
   }

   &__title {
      text-align: center;
      flex: 1 1 auto;
      @media screen and (max-width: 479.98px){
         margin: 0 10px;
      }
      
   }
   &__contacts{
      display: flex;
      align-items: center;
      
      @media screen and (max-width: 1086.98px){
         display: none;

      }

   }

   &__phone {
      font-size: 16px;
      font-weight: 600;
      opacity: 0.7;
      margin-right: 40px; 
      color: $typography;     
     
   }

   
   &__iconPhone {
      margin-right: 8px;
      
   }

   &__down {
      border-width: 1px 0px;
      border-style: solid;
      border-color: rgba(51, 51, 51, 0.1);
      padding: 28px 0;
      @media screen and (max-width: 1086.98px){
         display: none;
      }
   }

   &__list {
      display: flex;      
      margin: 0;
      padding: 0;
      align-items: center;
      justify-content: space-between;      
      font-weight: 500;
   }
   &__item {
      
      position: relative;
      padding: 0;
      list-style-type: none;
      text-align: center;
      /* margin-right: 40px; */
      &:last-child {
         margin: 0px;
      }         
      & a {   
         color: $typography;   
      }
   }   
   &__dropdown{
      text-align: center;
      margin: 2px auto;
   }
   &__children-wrapper {
      
      position: absolute;  
      top: 51px;
      left: 0;
      color: rgba($typography,0.1);
    }

    &__children {
      width: 352px;
      padding: 0;
      list-style-type: none;
      text-align: left;
      color: rgba($typography,0.1);
      background: $white;
      
    } 
    &__children-item{
      padding: 16px;
      
      border-bottom: 1px solid rgba(51, 51, 51, 0.1);
      & a {   
         color: rgba($typography,0.5);   
      }
    }
    &__children-link{
      position: relative;
    }
    &__children-hit{
      
      position: absolute;
      top: 16px;
      right: 0;
      background: url(../assets/image/icons/hits.png) no-repeat;
      background-size: cover;
      color: $white;
      font-size: 10px;
      padding: 3px 10px;

    }
}
a {      
   text-decoration: none;
   
   text-transform: uppercase;
   &:hover {
      color: $orange;
   }
   &:active{
      color: $grey;
      opacity: 0.3;
   }
}

</style>