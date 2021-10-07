<template>
  <div class="container px-5 mx-auto">
    <div class="flex flex-wrap -m-4">
      <div
        v-for="(article, index) in CutArticles(this.page)"
        :key="index"
        class="p-4 lg:w-1/3"
      >
        <div
          class="h-full bg-gray-100 bg-opacity-75 px-8 pt-16 pb-24 rounded-lg overflow-hidden text-center relative"
        >
          <h2
            class="tracking-widest text-xs title-font font-medium text-gray-400 mb-1"
          >
            ARTICLE
          </h2>
          <h1
            class="title-font sm:text-xl text-lg font-medium text-gray-900 mb-3"
          >
            {{ article.Titre }}
          </h1>
          <p class="leading-relaxed mb-3 text-xs">
            {{ article.Content }}
          </p>
          
            <a class="text-indigo-500 inline-flex items-center" v-on:click="rooter(index)"
              
              >Lire l'article
              
              <svg
                class="w-4 h-4 ml-2"
                viewBox="0 0 24 24"
                stroke="currentColor"
                stroke-width="2"
                fill="none"
                stroke-linecap="round"
                stroke-linejoin="round"
              >
                <path d="M5 12h14"></path>
                <path d="M12 5l7 7-7 7"></path>
              </svg>
            </a>
          
          
          <div
            class="text-center mt-2 leading-none flex flex-col justify-center absolute bottom-0 left-0 w-full py-4"
          >
            <p class="leading-relaxed">
              {{ article.Date }}
            </p>
            <p class="leading-relaxed mb-3">
              {{ article.Auteur }}
            </p>
          </div>
        </div>
      </div>
    </div>
    <p><button v-on:click="pageDown" v-bind:class="{ stop: VerifDown }">Page Précedente</button>-<button v-on:click="pageUp" v-bind:class="{ stop: isUp }">Page Suivante</button></p>
  </div>
</template>

<script>
import article from "../views/Article.vue"


export default {
  data(){
    return{
      page:0,
      
      isUp: false
    }
  },
  component:{
    article
  },
  
  computed: {
    VerifDown(){
      console.log(this.page)
      if(this.page == 0){
        return true
      }else{
        return false
      }
    },


    listArticle() {
      return this.$store.state.listArticle;
    },
    
  },
  methods: {
    
    pageUp(){
      this.page = this.page + 1
      return 1
    },
    pageDown(){
      this.page = this.page - 1
      return 1
    },
    rooter(index){
      console.log("ici")
      return this.$router.push({ name: 'Article', params: { id: index } })
    },
    troncText(text) {
      text = text.substring(0, 100);
      text = text + "...";
      return text;
    },
    
    CutArticles(index) {
      let article = [];
      let taille = 10;

      if (this.listArticle.length < index + 10) {
        taille = index + 10 - this.listArticle.length;
        taille = 10 - taille;

        taille = taille + index - 1;
      } else {
        taille = index + 10;
      }

      for (let i = index; i <= taille; i++) {
        article.push(this.listArticle[i]);
      }

      return article;
    },
  },
};
</script>
  
<style scoped>
/* img {
  width: 100%;
  height: 300px;
}
body {
  background-color: #dcdcdc;
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
}

.tableau {
  background-color: white;
  width: 99%;
  display: flex;
  flex-direction: column;
  border: solid 1px;
  margin-top: 10px;
  height: auto;

  box-shadow: 0px 10px 13px -7px #000000, 5px 5px 22px 6px rgba(0, 0, 0, 0);
}
table {
  width: 100%;
}

.first th {
  border: solid 1px;
  width: 100%;
}

.title {
  display: flex;
  width: 100%;
  justify-content: center;
}

.info {
  display: flex;
  flex-direction: row;
  width: 100%;
  justify-content: space-around;
}

div.tableau:hover {
  background-color: #d3d3d3;
  text-decoration: underline;
} */
.stop
{
  display: none;
}
</style>
