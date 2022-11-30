<template>
  <div>
    <div>{{ Film }}</div>
  </div>
</template>

<script>
export default {
    name: 'MainPage',
    props: {
        Film: Array,
    }
}
</script>

<style lang="scss" scoped>
    div {
        height: 85vh;
        background-color: #6b6b6b;
    }
</style>