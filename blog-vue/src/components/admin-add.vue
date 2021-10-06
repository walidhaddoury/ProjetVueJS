<template>
  <div class="h-full w-full p-4 flex flex-col justify-center items-center">
    <form
      ref="formArticle"
      class="w-full max-w-4xl"
      @submit.prevent="addArticle"
    >
      <div class="flex flex-wrap -mx-3 mb-6">
        <div class="w-full md:w-1/3 px-3 mb-6 md:mb-0">
          <label
            class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2"
            for="grid-first-name"
          >
            Titre
          </label>
          <input
            class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white"
            type="text"
            v-model="titre"
          />
        </div>
        <div class="w-full md:w-1/3 px-3 mb-6 md:mb-0">
          <label
            class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2"
            for="grid-last-name"
          >
            Auteur
          </label>
          <input
            class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white"
            type="text"
            v-model="auteur"
          />
        </div>
        <div class="w-full md:w-1/3 px-3 mb-6 md:mb-0">
          <label
            class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2"
          >
            Date
          </label>
          <input
            class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white"
            type="date"
            v-model="date"
          />
        </div>
        <div class="w-full md:w-3/3 px-3 mb-6 md:mb-0">
          <label
            class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2"
          >
            Content
          </label>
          <input
            class="text-justify h-40 appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white"
            type="text"
            v-model="content"
          />
        </div>
      </div>
      <div class="flex items-center justify-evenly">
        <button
          class="w-1/3 md:w-1/5 bg-red-500 hover:bg-red-700 text-white font-bold py-2 px-4 rounded focus:outline-none focus:shadow-outline"
          type="button"
        >
          Annuler
        </button>
        <button
          class="w-1/3 md:w-1/5 bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded focus:outline-none focus:shadow-outline"
          type="submit"
        >
          Valider
        </button>
      </div>
    </form>
    <div>
      <h1>{{ listArticle }}</h1>
    </div>
  </div>
</template>

<script>
export default {
  name: "admin-add",
  data: function() {
    return {
      titre: "",
      auteur: "",
      date: "",
      content: "",
      listArticle: [],
    };
  },
  methods: {
    addArticle: function() {
      if (
        this.titre != "" &&
        this.auteur != "" &&
        this.date != "" &&
        this.content != ""
      ) {
        this.listArticle.push({
          titre: this.titre,
          auteur: this.auteur,
          date: this.date,
          content: this.content,
        });
      }
      this.titre = this.auteur = this.date = this.content = "";
    },
  },
};
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  width: 80%;
  justify-content: center;
}

.form {
  display: flex;
  justify-content: center;
  align-items: center;
}
input[type="text"] {
  text-align: start;
}
</style>
