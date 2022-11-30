<template>
  <div>
    <HeaderPage @searchValue="results"/>
    <MainPage :Film="searchFilm"/>
  </div>
</template>

<script>
import HeaderPage from '@/components/HeaderPage.vue';
import MainPage from '@/components/MainPage.vue';
export default {
  name: 'App',
  components: {
    HeaderPage,
    MainPage,
  },
  data(){
    return {
      searchFilm: '',
    };
  },
  methods: {
    results(search){
      this.searchFilm = search;
    },
  },
};
</script>

<style>

</style>