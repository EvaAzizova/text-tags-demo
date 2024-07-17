<template>
  <v-container>
    <h1>Welcome to the Home Page</h1>
    <text-tags :tags="tags" alignment="justified"></text-tags>
  </v-container>
</template>

<script>
import TextTags from '../components/TextTags.vue';

export default {
  name: 'HomeView',
  components: {
    TextTags,
  },
  data() {
    return {
      tags: [
        { text: 'текст1' },
        { text: 'текст2', icon: 'mdi-star' },
        { text: 'текст3' },
        { text: 'текст4', icon: 'mdi-heart' },
        { text: 'текст5' },
      ],
    };
  },
};
</script>

<style scoped>
h1 {
  font-weight: normal;
}
</style>
