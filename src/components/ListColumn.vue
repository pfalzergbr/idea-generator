<template>
  <div class="column list-column">
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
<style>
  .list-column {
  /* display: grid; */
  /* grid-row: 1 /2 ;
  grid-column: 2/ 3; */
  }
</style>
