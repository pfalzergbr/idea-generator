<template>

    <ul class="ideas-field">
      <idea-item
        class="idea-item"
        v-for="(idea, index) in ideas"
        :key="idea.id"
        :idea="idea.idea"
        :index="index"
      ></idea-item>
    </ul>

</template>

<script>
import IdeaItem from './IdeaItem.vue';

export default {
  props: ['ideas'],
  components: {
    IdeaItem,
  },
};
</script>

<style lang="scss" scoped>
  .ideas-field {
    width: 100%;
  }
  

  .idea-item {
    padding: .5rem;
  }
</style>
