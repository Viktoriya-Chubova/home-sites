<template>
  <div class="home">
    <CoverHome></CoverHome>
    <AnticrisisHome :data="AnticrisisData"></AnticrisisHome>
  </div>
</template>

<script>
import CoverHome from '../components/CoverHome.vue';
import AnticrisisHome from '../components/AnticrisisHome.vue';
import {AnticrisisData} from '@/data/data.dummy'

// @ is an alias to /src


export default {
  name: 'Home',
  components: {
    CoverHome,
    AnticrisisHome
  },
  data(){
    return{
      AnticrisisData:AnticrisisData,
      
    }
  }
}
</script>
