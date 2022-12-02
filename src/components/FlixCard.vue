<template>
  <div>
    <ul>
      <li><img :src="imgUrl" alt=""></li>
      <li>Titolo: {{ title }}</li> 
      <li>Titolo Originale: {{ originalTitle }}</li> 
      <li>Lingua:<lang-flag :iso="language"/></li>
      <li><font-awesome-icon v-for="item in score.score" :key="item" icon="fa-solid fa-star" :style="{color: 'gold'}"/><font-awesome-icon v-for="item in (score.maxScore - score.score)" :key="item" icon="fa-regular fa-star" :style="{color: 'gold'}"/></li>
    </ul>
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
    }

}
</script>

<style>
    ul {
        list-style: none;
        border: 2px solid orange;
        padding: 1rem;
        margin: 1rem;
        height: 700px;
    }
</style>