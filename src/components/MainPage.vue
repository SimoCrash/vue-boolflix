<template>
  <div>
    <div v-for="(filme, index) in film" :key="index">{{ filme.original_title }}</div>
  </div>
</template>

<script>
export default {
    name: 'MainPage',
    props: {
        film: Array,
    }
}
</script>

<style lang="scss" scoped>
    div {
        height: 85vh;
        background-color: #6b6b6b;
    }
</style>