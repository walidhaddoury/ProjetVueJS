<template>
  
  <div style="width: 100%;">
    <ListArticle/>
  </div>
</template>



<script>
import ListArticle from './components/ListArticles.vue'
export default {
  name: 'List',
  components: {
    ListArticle
  }
}

</script>




<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
