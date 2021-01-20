<template>
  <div class="list__header">
    <ideas-title></ideas-title>
    <ideas-progress></ideas-progress>
    <idea-counter :numOfIdeas="numOfIdeas"></idea-counter>
    <add-idea v-if="numOfIdeas !== 20 ? true : false" @add-idea="newIdea"></add-idea>
    <div v-else>Good job!</div>
  </div>
</template>

<script>
import IdeasProgress from './IdeasProgress';
import IdeaCounter from './IdeaCounter';
import AddIdea from './AddIdea.vue';
import IdeasTitle from './IdeasTitle'

export default {
  components: {
    IdeasProgress,
    IdeaCounter,
    AddIdea,
    IdeasTitle
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
