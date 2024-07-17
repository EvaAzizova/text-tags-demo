<template>
  <div class="text-tags" :class="`text-tags--${alignment}`" ref="tagsContainer">
    <div v-for="(tag, index) in visibleTags" :key="index" class="text-tags__item">
      <span v-if="tag.icon">
        <v-icon>{{ tag.icon }}</v-icon>
      </span>
      <span>{{ tag.text }}</span>
      <v-icon v-if="index < visibleTags.length - 1" class="text-tags__separator">mdi-circle-small</v-icon>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TextTags',
  props: {
    tags: {
      type: Array,
      default: () => [],
    },
    alignment: {
      type: String,
      default: 'left', // or 'justified'
    },
  },
  data() {
    return {
      visibleTags: [],
    };
  },
  mounted() {
    this.updateVisibleTags();
    window.addEventListener('resize', this.updateVisibleTags);
  },
  beforeDestroy() {
    window.removeEventListener('resize', this.updateVisibleTags);
  },
  methods: {
    updateVisibleTags() {
      this.$nextTick(() => {
        const containerWidth = this.$refs.tagsContainer.clientWidth;
        let cumulativeWidth = 0;
        this.visibleTags = this.tags.filter((tag, index) => {
          const tagElement = this.$refs.tagsContainer.children[index];
          const tagWidth = tagElement ? tagElement.clientWidth : 0;
          if (cumulativeWidth + tagWidth <= containerWidth) {
            cumulativeWidth += tagWidth;
            return true;
          }
          return false;
        });
      });
    },
  },
};

</script>

<style scoped lang="scss">
.text-tags {
  display: flex;
  &--left {
    justify-content: flex-start;
  }
  &--justified {
    justify-content: space-between;
  }
  &__item {
    display: flex;
    align-items: center;
    margin-right: 8px;
  }
  &__separator {
    margin: 0 4px;
  }
}
</style>
