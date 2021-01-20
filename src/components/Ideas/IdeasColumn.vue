<template>
  <div class="column list-column">
    <div v-if="question === ''">
      <the-question @new-question="addQuestion"></the-question>
    </div>
    <div v-else>
      <ideas-header :question="question" :ideas="ideas" @add-idea="AddIdea"></ideas-header>
      <idea-list :ideas="ideas"></idea-list>
    </div>
  </div>
</template>

<script>
import IdeasHeader from './IdeasHeader.vue';
import IdeaList from './IdeaList.vue';
import TheQuestion from './TheQuestion'

export default {
  components: { IdeasHeader, IdeaList, TheQuestion },
  data() {
    return {
      ideas: [],
      chosenIdea: '',
      question: '',
    };
  },
  methods: {
    addIdea(idea) {
      const newIdea = {
        id: new Date().toISOString,
        idea,
      };
      this.ideas.push(newIdea);
    },
    addQuestion(question){
      this.question = question;
    }
  },
  computed: {
    filledIdeas() {
      return this.ideas.length === 20 ? true : false;
    },
  }
};
</script>
<style>

</style>
