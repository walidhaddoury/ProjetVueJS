<template>
  <div id="app" class="font">
    <div class="bg flex flex-col py-10 md:flex-row md:justify-between md:p-10">
      <div class="md:w-1/4 text-3xl text-center">
        <h1 class="font">BLOG VueJS</h1>
      </div>
      <div class="text-center md:w-3/4 text-3xl md:text-right">
        <router-link to="/">Home</router-link> |
        <router-link to="/article">Article</router-link> |
        <router-link to="/about">About</router-link> |
        <router-link to="/admin">Admin</router-link>
      </div>
    </div>
    <hr />
    <router-view />
  </div>
</template>

<style scoped>
.font {
  font-family: Avenir, Helvetica, Arial, sans-serif;
}
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  justify-content: center;
}

.bg {
  background-color: black;
  color: whitesmoke;
}

#nav {
  padding: 30px;
}

a {
  font-weight: bold;
  font-size: 30px;
}

a.router-link-exact-active {
  color: #42b983;
}
hr {
  size: 2px;
  background-color: black;
}
</style>
