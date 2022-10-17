<template>
   <button class="btn">      
      <slot>            
      </slot>      
   </button>
</template>

<script>
   export default {
      
   }
</script>

<style lang="scss" scoped>
@import "../assets/layouts/index.scss";
.btn {
   display: flex;
   align-items: center;
   justify-content: center;
   font-weight: 500;
   font-size: 16px;
   color: $orange;
   border: 1px solid #FF5900;
   border-radius: 100px;
   background: rgba($white, 0);
   padding: 16px 28px;
   
   &:hover{
      color: $white;
      background-color: $orangeDark;
   }
   &:active{
      color: rgba($white,0.3);
   }
}
</style>