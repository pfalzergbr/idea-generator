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
  },
};
</script>

<style lang="scss">

@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;700&family=Quicksand:wght@300;400;700&display=swap');

$color-orange-light-1: #f5f2eb;
$color-orange-light-2: #f7d1a8;
$color-orange-light-3: #ffb563;
$color-grey-medium: #7b7460;
$color-grey-dark-1: #423e34;
$color-grey-dark-2: #1d1c19;


$font-size-sm: 1rem;
$font-size-md: 1.2rem;
$font-size-lg: 1.6rem;
$font-size-xl: 3.2rem;


*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

html {
  background: $color-orange-light-1;
  font-size: 10px;
}

body {
  font-family: 'Montserrat';
  font-size: $font-size-lg;
}

h1,
h2,
h3 {
  font-family: 'Quicksand';
  color: $color-grey-dark-2;
}

h1 {
  font-size: $font-size-xl;
}

p {
  color: $color-grey-dark-2;
}

.app {
  min-height: 75vh;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
  grid-template-rows: 75vh;
  grid-column-gap: 2.5rem;
  grid-row-gap: 2.5rem;
  margin: 5rem;
}

.column {
  background: $color-orange-light-3;
  padding: 5rem;
  border-radius: 1rem;
}
</style>
