<template>
   <div>                 
         <div class="burgermenu" @click="showBurger = !showBurger">                  
            <a href="#" type="button" class="burgermenu__burger" v-if="!showBurger">
               <img class="burgermenu__image" src="../assets/image/icons/openmenu.svg" alt="">                         
            </a> 
            <a href="#" type="button" class="burgermenu__burger" v-else>
               <img class="burgermenu__image" src="../assets/image/icons/closemenu.svg" alt="">                                   
            </a>                                     
         </div>
         <transition name="burger">
            
            <ul class="burgermenu__list" v-if="showBurger">                        
               <li class="burgermenu__item" v-for="item in data" :key="item.id" >                  
                  <router-link  href="" :to="item.path" @click=toggle(item.dropdown)  >{{item.name}}                     
                     <img class="burgermenu__dropdown" v-if="item.dropdown" src="../assets/image/icons/dropdown.png" alt="">
                     <div class="header__children-wrapper" v-if="item.dropdown">
                        <ul class="burgermenu__children"  v-show="show">
                           <li class="burgermenu__children-item"   v-for="index in item.dropdown" :key="index.id">
                              <router-link  href="" :to="index.path"  @click="close" >{{index.name}}</router-link>
                           </li>                           
                        </ul>
                     </div>
                  </router-link> 
               </li>   
               
               <div class="burgermenu__contacts">               
                  <AppButton>
                     <img class="burgermenu__iconPhone" src="../assets/image/icons/phone.svg" alt="">
                     Заказать звонок
                  </AppButton>
                  <a class="burgermenur__phone" href="tel:+74872792910">+7 (4872) 79-29-10</a>
               </div>  
                                        
            </ul> 
             
         </transition>
         
      </div> 
</template>

<script>
import AppButton from './AppButton.vue';
   export default {
    name: "Burger",
    props: {
        data: {
            type: Array,
            default: () => [], //возвращает пустой массив
        },
    },
    data() {
        return {
            showBurger: false,
            show: false,
            indexMenu: 0
        };
    },
    methods: {
      toggle(isDropdown) { 
         if(isDropdown){
            this.show = !this.show    
         }
         else{
            this.showBurger = false 
         }        
            
      },     
      close(){
         this.showBurger = false 
         this.show = false 
      } 
    },
    components: { AppButton }
}
</script>

<style lang="scss" scoped>
@import "../assets/layouts/index.scss";
.burgermenu{
   display: none;
      
   @media screen and (max-width: 1086.98px){
      display: block;
   }
   &__burger{             
      display: flex;
      justify-content: flex-end;
      width: 35px;
   }
   &__list {      
      display: none;
      position: absolute;
      top: 104px;
      right: 0;
      width: 350px;   
      height: 600px;   
      text-transform: uppercase;  
      list-style-type: none;  
      margin: 0;
      padding: 0;
      padding-top: 20px;  
      font-weight: 700;           
      background-color: $grey;      
      
      
      @media screen and (max-width: 1086.98px){
         display: block;
      }   
      @media screen and (max-width: 767.98px){
         width: 100%;         
         top: 82px;
      
      }
      & a {      
         text-decoration: none;
         color: $white;  
      }
   }
   &__item {
      text-align: right;     
      padding: 5px 36px;
      @media screen and (max-width: 767.98px){
         text-align: center;             
      
      }
      
   }
   &__contacts{
      display: flex;
      align-items: flex-end;
      flex-direction: column;
      margin-top: 30px;
      gap: 30px;
      margin-right: 30px;
      @media screen and (max-width: 767.98px){
         align-items: center;
         margin-right: 0px;
      
      }
   }

   &__phone {
      font-size: 16px;
      font-weight: 600;
      opacity: 0.7;
      
      
   }

   
   &__iconPhone {
      margin-right: 8px;
      
   }
   &__dropdown{
      text-align: center;
      margin: 2px auto;
   }
   

   &__children-wrapper {
      
     
      color: rgba($typography,0.1);
    }

    &__children {
     
      padding: 15px;
      list-style-type: none;
      
      
      
      
    } 
    &__children-item{
      padding: 5px;
      
      
      & a {   
         color: rgba($white,0.5);   
      }
    }
}

.burger-enter-active,
.burger-leave-active {
  transition: opacity 0.3s ease;
}
.burger-enter-from,
.burger-leave-to {
  opacity: 0;
}
</style>