<template>
  <div>
    <h2>Movies</h2>
    <ul v-for="films in film" :key="films.id">
      <li>Titolo: {{ films.title }}</li> 
      <li>Titolo Originale: {{ films.original_title }}</li> 
      <li>Lingua: {{ films.original_language }} <lang-flag :iso="films.original_language"/></li>
      <li>Voto: {{ films.vote_average }}</li>
    </ul>

    <h2>Series</h2>
    <ul v-for="TvSeries in arrTvFound" :key="TvSeries.id">
      <li>Titolo: {{ TvSeries.title }}</li> 
      <li>Titolo Originale: {{ TvSeries.original_title }}</li> 
      <li>Lingua: {{ TvSeries.original_language }} <lang-flag :iso="TvSeries.original_language"/></li>
      <li>Voto: {{ TvSeries.vote_average }}</li>
      
    </ul>
  </div>
</template>

<script>
export default {
    name: 'MainPage',
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
</style>