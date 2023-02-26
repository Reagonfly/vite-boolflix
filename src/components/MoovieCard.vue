<script>
export default {
    props:{
        moovie: Object
    },
    posterImage(value) {
      if (value.poster_path) {
        return `https://image.tmdb.org/t/p/w342${value.poster_path}`
      }
      else {
        return `https://ih1.redbubble.net/image.2426525830.1498/fposter,small,wall_texture,product,750x1000.jpg`
      }
    },
    //Funzione per le bandiere
    getFlag(value) {
      let lang = '';
      if (value.original_language) {
        switch (value.original_language) {
          default:
            lang = (value.original_language)
            break;
          case 'en':
            lang = 'gb'
            break;
          case 'ja':
            lang = 'jp'
            break;
        }
        let urlFlag = lang.toUpperCase()
        return urlFlag
      }
    },
    //Funzione stelle 
    filledStars() {
      let starFull = Math.round(this.details.vote_average / 2);
      let starsFilledArr = [];
      for (let i = 0; i < starFull; i++) {
        starsFilledArr.push('fa-solid fa-star');
      }
      //Implementazione stelle vuote
      let starEmpty = 5 - starFull;
      for (let i = 0; i < starEmpty; i++) {
        starsFilledArr.push('fa-regular fa-star');
      }
      return starsFilledArr
    },
    overviewEmpty(details) {
      if (details.overview == '') {
        return 'La descrizione non è disponibile.'
      }
      else {
        return `${this.details.overview}`
      }
    }
}
    
</script>

<template lang="">
    <div class="col-5 moovie text-center m-3 p-2">
        <img class="img-fluid" :src="moovie.poster_path" :alt="moovie.title">
        <h4 class="my-2">{{ moovie.title }}</h4>
        <div class="my-1"><strong>Year: </strong>{{ moovie.release_date }}</div>
        <div><strong>Vote:</strong> {{ moovie.vote_average }} <strong>Language: </strong>{{ moovie.original_language }}</div>
    </div>
</template>

<style lang="scss" scoped>
    @use '../styles/generals.scss' as *;
    @use '../styles/partials/mixins.scss' as *;

</style>