<template>
  <div>
    <HeaderPage @searchValue="results"/>
    <MainPage :film="arrFilmFound" :arrTvFound="arrTvFound"/>
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
      baseApiUrl: 'https://api.themoviedb.org/3',
      apiKey: 'eddeb9cc139fc5540af4fe0bcd294c59',
      resultsLanguage: 'it-IT',
      arrFilmFound: null,
      arrTvFound: null,
    };
  },
  methods: {
    results(search){
      axios.get(this.baseApiUrl + '/search/movie', {
        params: {
          api_key: this.apiKey, 
          query: search,
          language: this.resultsLanguage,
        },
      })
      .then(axiosResponse => {
        this.arrFilmFound = axiosResponse.data.results;
      });

      axios.get(this.baseApiUrl + '/search/movie', {
        params: {
          api_key: this.apiKey, 
          query: search,
          language: this.resultsLanguage,
        },
      })
      .then(axiosResponse => {
        this.arrTvFound = axiosResponse.data.results;
      })
    },
  },
};
</script>

<style lang="scss">
  h2 {
    margin-top: 0;
  }
</style>



