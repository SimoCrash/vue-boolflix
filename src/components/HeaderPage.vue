<template>
  <div>
    <div class="container-header">
        <img src="https://boolflix.netlify.app/img/logo.png" alt="">
        <input type="text" placeholder="Cerca film..." 
        v-model="textToSearch"
        @change="$emit('searchValue', textToSearch)">
    </div>
  </div>
</template>

<script>
export default {
    name: 'HeaderPage',
    data(){
        return {
            textToSearch: '',
        };
    },

};
</script>

<style lang="scss" scoped>
    .container-header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        background-color: black;
        height: 15vh;
        img, input {
            margin: 1rem;
        }
    }
</style>



