<template>
  <div class="w-full h-full p-10">
    <div class="text-5xl mb-20">
      <h1>Nos Articles du moment</h1>
    </div>
    <ListArticles />
  </div>
</template>

<script>
// @ is an alias to /src
import ListArticles from "@/components/ListArticles.vue";

export default {
  name: "Home",
  components: {
    ListArticles,
  },
};
</script>
