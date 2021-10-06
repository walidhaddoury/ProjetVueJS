<template>
  <div class="w-full flex flex-col items-center pt-8">
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
              v-for="(article, index) in listArticle"
              :key="index"
              class="text-gray-700"
            >
              <td class="px-4 py-3 text-ms font-semibold border">
                {{ article.Titre }}
              </td>
              <td class="px-4 py-3 text-ms border">{{ article.Auteur }}</td>
              <td class="px-4 py-3 text-ms border">
                {{ article.Content }}
              </td>
              <td class="px-4 py-3 text-sm border">{{ article.Date }}</td>
              <td class="px-4 py-3 text-sm border">
                <button
                  :value="index"
                  class="w-4"
                  @click="deleteArticle(index)"
                >
                  <img src="../assets/remove.png" alt="" />
                </button>
              </td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  computed: {
    listArticle() {
      return this.$store.state.listArticle;
    },
  },
  methods: {
    deleteArticle(index) {
      return this.$store.dispatch("removeArticleById", index);
    },
  },
};
</script>
