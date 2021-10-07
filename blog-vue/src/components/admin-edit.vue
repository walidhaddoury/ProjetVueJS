<template>
  <div>
    <div
      v-if="!defaultScreen"
      class="w-full p-4 flex flex-col justify-center items-center"
    >
      <form ref="formArticle" class="w-full max-w-4xl" @submit.prevent="">
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
              type="text"
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
            @click="resetInput, (defaultScreen = true)"
          >
            Annuler
          </button>
          <button
            class="w-1/3 md:w-1/5 bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded focus:outline-none focus:shadow-outline"
            type="submit"
            @click="updateArticle(), (defaultScreen = true)"
          >
            Valider
          </button>
        </div>
      </form>
    </div>
    <div v-if="defaultScreen" class="w-full flex flex-col items-center pt-8">
      <div class="w-10/12 mb-8 overflow-hidden rounded-lg shadow-lg">
        <div class="w-full overflow-x-auto">
          <table class="w-full">
            <thead>
              <tr
                class="text-md font-semibold tracking-wide text-left text-gray-900 bg-gray-100 uppercase border-b border-gray-600"
              >
                <th class="px-4 py-3">Titre</th>
                <th class="px-4 py-3">Auteur</th>
                <th class="px-4 py-3">Content</th>
                <th class="px-4 py-3">Date</th>
                <th></th>
              </tr>
            </thead>
            <tbody class="bg-white">
              <tr
                v-for="(displayArticle, index) in listArticle"
                :key="index"
                class="text-gray-700"
              >
                <td class="px-4 py-3 text-ms font-semibold border">
                  {{ displayArticle.Titre }}
                </td>
                <td class="px-4 py-3 text-ms border">
                  {{ displayArticle.Auteur }}
                </td>
                <td class="px-4 py-3 text-ms border">
                  {{ displayArticle.Content }}
                </td>
                <td class="px-4 py-3 text-sm border">
                  {{ displayArticle.Date }}
                </td>
                <td class="px-4 py-3 text-sm border">
                  <button
                    :value="index"
                    class="w-4"
                    @click="
                      getArticle(displayArticle, index), (defaultScreen = false)
                    "
                  >
                    <img src="../assets/modify.svg" alt="" />
                  </button>
                </td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "admin-edit",
  data() {
    return {
      defaultScreen: true,
      indexToChange: null,
      titre: "",
      date: "",
      auteur: "",
      content: "",
    };
  },
  computed: {
    listArticle() {
      return this.$store.state.listArticle;
    },
  },
  methods: {
    getArticle(article, index) {
      this.titre = article.Titre;
      this.auteur = article.Auteur;
      this.date = article.Date;
      this.content = article.Content;
      this.indexToChange = index;
    },
    updateArticle() {
      if (
        this.titre != "" &&
        this.auteur != "" &&
        this.date != "" &&
        this.content != ""
      ) {
        this.$store.dispatch("updateArticle", [
          {
            Titre: this.titre,
            Auteur: this.auteur,
            Date: this.date,
            Content: this.content,
          },
          this.indexToChange,
        ]);
        this.resetInput();
      }
    },
    resetInput() {
      this.titre = this.auteur = this.date = this.content = "";
    },
  },
};
</script>
