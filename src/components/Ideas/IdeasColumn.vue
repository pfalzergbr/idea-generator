<template>
  <div class="column list-column">
    <div v-if="question === ''">
      <the-question @new-question="addQuestion"></the-question>
    </div>
    <div class="ideas-container" v-else>
      <ideas-header :question="question" :ideas="ideas" @add-idea="addIdea"></ideas-header>
      <idea-list v-if="ideas.length !== 0" :ideas="ideas"></idea-list>
      <p class="no-ideas" v-else> No ideas yet. Add some to the list!</p>
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
<style lang="scss" scoped>
  .ideas-container {
    height: 100%;
    width: 100%;
    display: flex;
    flex-direction: column;
  }

  .no-ideas {
    margin-left: 1rem;
  }

</style>
