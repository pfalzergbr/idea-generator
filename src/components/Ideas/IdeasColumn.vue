<template>
  <div class="column list-column">
    <!-- <div v-if="question === ''"> -->

    <!-- </div> -->
    <div class="ideas-container">
      <ideas-header :question="question" :ideas="ideas" @add-idea="addIdea"></ideas-header>
      <idea-list v-if="ideas.length !== 0" :ideas="ideas"></idea-list>
      <p class="no-ideas" v-else> No ideas yet. Add some to the list!</p>
    </div>
    <choose-idea v-if="filledIdeas" ></choose-idea>
  </div>
</template>

<script>
import IdeasHeader from './IdeasHeader.vue';
import IdeaList from './IdeaList.vue';

import ChooseIdea from './ChooseIdea';

export default {
  props: ['question'],
  components: { IdeasHeader, IdeaList, ChooseIdea },
  data() {
    return {
      ideas: [],
      chosenIdea: '',
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
  },
  computed: {
    filledIdeas() {
      return this.ideas.length === 20 ? true : false;
    },
  }
};
</script>
<style lang="scss" scoped>
  .list-column {
    display: flex;
    flex-direction: column;
    justify-content: space-between
  }

  .ideas-container {
    width: 100%;
    display: flex;
    flex-direction: column;
  
  }

  .no-ideas {
    margin-left: 1rem;
  }

</style>
