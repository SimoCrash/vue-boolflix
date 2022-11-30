<template>
  <div>
    <HeaderPage @searchValue="results"/>
    <MainPage :Film="filmFound"/>
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
      filmFound: null,
    };
  },
  methods: {
    results(search){
      this.filmFound = search;
      axios.get('https://api.themoviedb.org/3/search/movie', {
        params: {
          api_key: 'eddeb9cc139fc5540af4fe0bcd294c59', 
          query: this.filmFound,
        }
      })
      .then(axiosResponse => {
        this.filmFound = axiosResponse.data.results
      })
    },
  },
};
</script>

<style>

</style>



