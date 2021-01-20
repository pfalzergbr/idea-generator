<template>
  <div class="column list-column">
      <!-- <the-question @new-question="addQuestion"></the-question> -->
    <div>
      <ideas-header :question="question" :ideas="ideas" @add-idea="newIdea"></ideas-header>
      <idea-list :ideas="ideas"></idea-list>
      <the-question></the-question>
    </div>
  </div>
</template>

<script>
import IdeasHeader from './IdeasHeader.vue';
import IdeaList from './IdeaList.vue';
import TheQuestion from './TheQuestion'

export default {
  components: { IdeasHeader, IdeaList, TheQuestion },
  props: ['ideas', 'question'],
  methods: {
    newIdea(idea) {
      this.$emit('add-idea', idea);
    },
  },
};
</script>
<style>

</style>
