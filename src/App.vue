<script>
import axios from 'axios';
import AppHeader from './components/AppHeader.vue';
import AppContent from './components/AppContent.vue';

export default {
    components:{
      AppHeader,
      AppContent
    },
    data(){
      return{
        moovieList: [],
        url: "https://api.themoviedb.org/3/search/movie?api_key=e99307154c6dfb0b4750f6603256716d&query=ritorno+al+fut"
      }
    },
    created(){
      this.getMoovies();
    },
    methods:{
      getMoovies(){
        axios.get(this.url).then((response) => {
          this.moovieList = response.data.results
        })
      }
    }
}
</script>
<template lang="">
  <div>
    <AppHeader message="Boolflix" />
    <main>
      <AppContent :moovies="moovieList" />
    </main>
  </div>
</template>
<style lang="scss">
  @use './styles/generals.scss' as *;

</style>