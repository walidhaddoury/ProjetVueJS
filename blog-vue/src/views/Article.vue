<template>
  <div class="p-20 article w-full h-5/6">
    <div class="text-center mb-20">
      <h1 class="text-5xl">{{ articles.Titre }}</h1>
      <h3 class="text-xl">{{ articles.Auteur }} | {{ articles.Date }}</h3>
    </div>
    <p class="text-lg mb-20 text-left">{{ articles.Content }}</p>
    <img
      src="https://game-guide.fr/wp-content/uploads/2014/11/Overwatch_Poster_Final.jpg"
      alt=""
    />
  </div>
</template>

<style>
.article {
  animation: article ease 5s;
  -webkit-animation: article ease 5s;
  -moz-animation: article ease 5s;
  -o-animation: article ease 5s;
  -ms-animation: article ease 5s;
}

@keyframes article {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

@-moz-keyframes article {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

@-webkit-keyframes article {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

@-o-keyframes article {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

@-ms-keyframes article {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
</style>

<script>
export default {
  computed:{
    articleId(){
      console.log(this.$route.params.id)
      return this.$route.params.id;
    },
    articles(){
      return this.$store.state.listArticle[this.articleId]
    }
  },
  
};
</script>
