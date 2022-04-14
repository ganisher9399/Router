<template>
  <div class="home">
    <h1>UzNewsHot</h1>
    <div class="wrapper">
      <news-card 
      v-for="post in news"
      :key="post.id"
      :img="post.img"
      :title="post.title"
      @action="$router.push({ name: 'About', params: { id: post.id }})"
      />
    </div>
  </div>
</template>

<script>
import NewsCard from "../components/NewsCard.vue"
import NewsArray from "../news.js"

export default {
  name: 'HomeView',
  components: {
    NewsCard,
  },

  data() {
    return {
      news: NewsArray
    }
  }
 
}
</script>

<style lang="scss" scoped>
  h1{
    text-align: center;
    margin: 50px 0;
  }

  .wrapper{
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    gap: 30px;
    width: 1400px;
    margin: 0 auto;
    padding-bottom: 100px;
  }
</style>