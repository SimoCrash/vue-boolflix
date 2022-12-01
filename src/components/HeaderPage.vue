<template>
  <div>
    <div class="container-header">
        <img src="https://boolflix.netlify.app/img/logo.png" alt="">
        <div>
            <form @submit.prevent="$emit('searchValue', textToSearch)">
                <label for="query">
                    <input type="text" placeholder="Cerca film..." 
                    v-model="textToSearch">
                </label>
                <button>Cerca</button>
            </form>
        </div>
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
    methods: {

    }

};
</script>

<style lang="scss" scoped>
    .container-header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        background-color: black;
        height: 15vh;
        img, input, button {
            margin: 1rem;
        }
    }
</style>



