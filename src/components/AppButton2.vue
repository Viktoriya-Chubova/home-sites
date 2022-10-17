<template>
   <button class="btn"
   :class="{
      'btn_orange': variant === 'orange',
      'btn_white': variant === 'white'
   }">      
      <slot>            
      </slot>      
   </button>
</template>

<script>
   export default {
      name: 'button',
      props: {
         variant :{
            type: String,
            default: 'orange'
         }
      }
   }
</script>

<style lang="scss" scoped>
@import "../assets/layouts/index.scss";
.btn {
   font-weight: 500;
   font-size: 18px;   
   border-radius: 100px;
  
   padding: 20px 40px;
   &_orange{
      color: $white;
      border: 1px solid $orange;
      background: $orange;
      &:hover{      
         background-color: $orangeDark;
      }
      &:active{
         color: rgba($white,0.3);
      }
   }
   &_white{
      color: $white;
      border: 1px solid $white;
      background: rgba(255, 255, 255, 0.2);
      &:hover{      
         border: 1px solid $orange;
         color: $orange;
      }
      &:active{
         color: rgba($orange,0.5);
      }
   }
}
@media screen and (max-width: 479.98px){
   .btn {
   font-size: 14px;   
  
   padding: 20px 25px;

}
}
</style>