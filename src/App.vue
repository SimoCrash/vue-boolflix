<template>
  <div>
    <HeaderPage @searchValue="results"/>
    <MainPage :Film="searchFilm"/>
  </div>
</template>

<script>
import HeaderPage from '@/components/HeaderPage.vue';
import MainPage from '@/components/MainPage.vue';
import axios from 'axios';
export default {
  name: 'App',
  components: {
    HeaderPage,
    MainPage,
  },
  data(){
    return {
      searchFilm: '',
      filmFound: null,
    };
  },
  methods: {
    results(search){
      this.searchFilm = search;
    },
  },
  mounted(){
    axios.get('https://api.themoviedb.org/3/search/movie', {
      params: {
        api_key: 'eddeb9cc139fc5540af4fe0bcd294c59', 
        query: this.searchFilm,
      }
    })
    .then(axiosResponse => {
      this.filmFound = axiosResponse.
    })
  }
};
</script>

<style>

</style>



