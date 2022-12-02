<template>
  <div>
    <h1 v-if="film.length">Movies</h1>
    <div class="container"
    >
      <FlixCard 
        v-for="films in film" :key="films.id"
        :title="films.title"
        :originalTitle="films.original_title"
        :language="films.original_language"
        :score="convertStar(films.vote_average)"
        :imgUrl="baseApiUrlImg + films.poster_path"
      />
    </div>
    

    

    <h1 v-if="arrTvFound.length">Series</h1>
    <div class="container">
      <FlixCard 
        v-for="TvFound in arrTvFound" :key="TvFound.id"
        :title="TvFound.name"
        :originalTitle="TvFound.original_name"
        :language="TvFound.original_language"
        :score="convertStar(TvFound.vote_average)"
        :imgUrl="baseApiUrlImg + TvFound.poster_path"
      />
    </div>
    <!-- <ul v-for="TvSeries in arrTvFound" :key="TvSeries.id">
      <li>Titolo: {{ TvSeries.title }}</li> 
      <li>Titolo Originale: {{ TvSeries.original_title }}</li> 
      <li>Lingua: {{ TvSeries.original_language }} <lang-flag :iso="TvSeries.original_language"/></li>
      <li>Voto: {{ TvSeries.vote_average }}</li>     
    </ul> -->
  </div>
</template>

<script>
import FlixCard from '@/components/FlixCard.vue';
export default {
    name: 'MainPage',
    components: {
      FlixCard,
    },
    data(){
      return {
      baseApiUrlImg: 'https://image.tmdb.org/t/p/w342',

      } 
    },
    methods: {
      convertStar(score){
        const maxScore = 5;
        const originalMaxScore = 10;
        return {
          score: Math.ceil((score * maxScore) / originalMaxScore),
          maxScore
        }
      },
    },
    props: {
        film: Array,
        arrTvFound: Array,
    }
}
</script>

<style lang="scss" scoped>
    div {
        background-color: #dbdbdb;
    }
    
    h1 {
      text-align: center;
      color: #b01d00;
    }
    .container {
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        gap: 1rem;
    }
</style>