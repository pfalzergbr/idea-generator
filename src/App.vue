<template>
  <div class="app">
    <rules-column></rules-column>
    <list-column :ideas="ideas" @add-idea="addIdea"></list-column>
    <idea-box v-if="filledIdeas"></idea-box>
  </div>
</template>

<script>
import ListColumn from './components/ListColumn.vue';
import RulesColumn from './components/RulesColumn';
import IdeaBox from './components/IdeaBox';

export default {
  name: 'App',
  components: {
    RulesColumn,
    ListColumn,
    IdeaBox,
  },
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
        id:new Date().toISOString,
        idea
      }
      this.ideas.push(newIdea);
    }
  },
  computed: {
    filledIdeas() {
      return this.ideas.length === 20 ? true : false;
    },
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

// .app {
//   width: 100vw;
//   height: 100vh;
//   display: grid;
//   grid-template-columns: 5vw, minmax(45%, 1fr) minmax(45%, 1fr) 5vw;
//   grid-template-rows: 5vh, 6fr 1fr 5vh;
// }

// .column {
//   width: 45%;
// }
</style>
