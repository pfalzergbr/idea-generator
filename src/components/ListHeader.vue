<template>
  <div>
    <list-progress></list-progress>
    <idea-counter :numOfIdeas="numOfIdeas"></idea-counter>
    <add-idea v-if="numOfIdeas !== 20 ? true : false" @add-idea="newIdea"></add-idea>
    <div v-else>Good job!</div>
  </div>
</template>

<script>
import ListProgress from './ListProgress';
import IdeaCounter from './IdeaCounter';
import AddIdea from './AddIdea.vue';

export default {
  components: {
    ListProgress,
    IdeaCounter,
    AddIdea,
  },
  props: ['ideas'],
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

<style></style>
