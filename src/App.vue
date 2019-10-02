<template>
  <div id="app">
    
    <Post 
      v-for="(post, index) in posts"
      :key="index"
      :id="post.id"
      :title="post.title"
      :description="post.description"
      :likes="likes.filter(like => like.post_id === post.id)"
      @like="handleLike"
      ></Post>
    <!-- <Inventory/> -->
  </div>
</template>

<script>
import Inventory from './components/Inventory.vue'
import Post from './components/Post.vue'

export default {
  name: 'app',
  data: function() {
    return {
      posts: [
        { id: 1, title: 'prova1', description: 'questo è un post di prova' },
        { id: 2, title: 'prova2', description: 'questo è un post di prova' },
        { id: 3, title: 'prova3', description: 'questo è un post di prova' },
      ],
      likes: []
    }
  },
  methods: {
    handleLike({ post_id, from }) {
      this.likes.push({ post_id, from })
    }
  },
  components: {
    Inventory,
    Post
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
