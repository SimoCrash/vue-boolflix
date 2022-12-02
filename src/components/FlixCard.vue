<template>
  <div>
    <div
        v-on:mouseenter="mouseenter"
        v-on:mouseleave="mouseleave"
    >
      <div v-if="message === true"><img :src="imgUrl" alt=""></div>
      <div v-if="message === false">
        <div>Titolo: {{ title }}</div> 
        <div>Titolo Originale: {{ originalTitle }}</div> 
        <div>Lingua:<lang-flag :iso="language"/></div>
        <div><font-awesome-icon v-for="item in score.score" :key="item" icon="fa-solid fa-star" :style="{color: 'gold'}"/><font-awesome-icon v-for="item in (score.maxScore - score.score)" :key="item" icon="fa-regular fa-star" :style="{color: 'gold'}"/></div>
      </div>
  </div>
  </div>
</template>

<script>
export default {
    name: 'FlixCard',
    props: {
        title: String,
        originalTitle: String,
        language: String,
        score: Number,
        imgUrl: String
    },
    data() {
        return {
            message: true,
        }
    },
    methods: {
        mouseenter: function(){
        this.message = false;
      },
      mouseleave: function(){
        this.message = true;
      }
    }

}
</script>

<style>

</style>