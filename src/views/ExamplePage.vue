<template>
  <v-container>
    <text-tags
      :tags="tags"
      alignment="left"
    />
  </v-container>
</template>

<script>
import TextTags from '@/components/TextTags.vue';

export default {
  name: 'ExamplePage',
  components: {
    TextTags,
  },
  data() {
    return {
      tags: [
        { text: 'ExampleTag1' },
        { text: 'ExampleTag2' },
        { text: 'ExampleTag3' },
      ],
    };
  },
};
</script>
