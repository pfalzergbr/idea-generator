<template>
  <div class="header">
    <ideas-title :question="question"></ideas-title>
    <idea-counter :numOfIdeas="numOfIdeas"></idea-counter>
    <add-idea v-if="numOfIdeas !== 20 ? true : false" @add-idea="newIdea"></add-idea>
    <div v-else>Good job!</div>
  </div>
</template>

<script>
import IdeaCounter from './IdeaCounter';
import AddIdea from './AddIdea.vue';
import IdeasTitle from './IdeasTitle'

export default {
  components: {
    IdeaCounter,
    AddIdea,
    IdeasTitle
  },
  props: ['ideas', 'question'],
  computed: {
    numOfIdeas() {
      return this.ideas.length;
    },
  }, methods: {
    newIdea(idea) {
      this.$emit('add-idea', idea)
    }
  }
};
</script>

<style lang="scss" scoped>
  .header {
    display: flex;
    flex-direction: column;
    justify-content: center;
  }
</style>
