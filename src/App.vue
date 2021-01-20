<template>
  <div class="app">
    <rules-column @new-question="addQuestion"></rules-column>
    <ideas-column :question="question" :ideas="ideas" @add-idea="addIdea"></ideas-column>
    <idea-box v-if="filledIdeas"></idea-box>
  </div>
</template>

<script>
import IdeasColumn from './components/Ideas/IdeasColumn.vue';
import RulesColumn from './components/Rules/RulesColumn';


export default {
  name: 'App',
  components: {
    RulesColumn,
    IdeasColumn,
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
    addQuestion(question){
      this.question = question;
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
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;700&family=Quicksand:wght@300;400;700&display=swap');

$color-orange-light-1: #f5f2eb;
$color-orange-light-2: #f7d1a8;
$color-orange-light-3: #ffb563;
$color-orange-bright: #ec9432;
$color-grey-medium: #7b7460;
$color-grey-dark-1: #423e34;
$color-grey-dark-2: #1d1c19;
$color-purple-medium: #c7abde;

$font-size-sm: 1rem;
$font-size-md: 1.6rem;
$font-size-lg: 2.4rem;
$font-size-xl: 3.2rem;
$font-size-xxl: 4.2rem;

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
  font-size: $font-size-md;
}

h1,
h2,
h3 {
  font-family: 'Quicksand';
  color: $color-grey-dark-2;
}

h1 {
  font-size: $font-size-xxl;
  font-weight: 700;
}

h2 {
  font-size: $font-size-lg;
  font-weight: 300;
}

p {
  color: $color-grey-dark-2;
}

input,
textarea {
  outline: none;
  border-radius: 0;
  background: $color-orange-light-3;
  border: 3px solid $color-orange-light-2;
  font-size: $font-size-md;
  color: $color-grey-dark-2;
  font-family: 'Quicksand';
}

input {
  padding: 1rem;
}

button {
  border: none;
  border-radius: 0;
  outline: none;
  padding: 1rem 2rem;
  font-family: 'Quicksand';
  border: 3px solid $color-orange-light-2;
  background: #f7d1a8;
  font-size: 1.6rem;
  text-transform: uppercase;
  transition: all 0.1s;
  cursor: pointer;

  &:hover,
  &:focus {
    background: $color-orange-bright;
    border: 3px solid $color-orange-bright;
  }
}

.app {
  min-height: 75vh;
  display: grid;
  // grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
  grid-template-columns: 2fr 3fr;
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
