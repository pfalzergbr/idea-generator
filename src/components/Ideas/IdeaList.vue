<template>
  <div>
    <ul>
      <idea-item
        v-for="(idea, index) in ideas"
        :key="idea.id"
        :idea="idea.idea"
        :index="index"
      ></idea-item>
    </ul>
  </div>
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

<style></style>
