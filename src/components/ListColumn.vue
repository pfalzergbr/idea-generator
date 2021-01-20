<template>
  <div class="column">
    <list-header :ideas="ideas" @add-idea="newIdea"></list-header>
    <idea-list :ideas="ideas"></idea-list>
  </div>
</template>

<script>
import ListHeader from './ListHeader.vue';
import IdeaList from './IdeaList.vue';

export default {
  components: { ListHeader, IdeaList },
  props: ['ideas'],
  methods: {
    newIdea(idea) {
      this.$emit('add-idea', idea);
    },
  },
};
</script>

<style></style>
