<template>
  <div class="column rules-column">
    <rules-header></rules-header>
    <rules-body></rules-body>
    <the-question @new-question="addQuestion"></the-question>

  </div>
</template>

<script>
import TheQuestion from './TheQuestion';
import RulesHeader from './RulesHeader';
import RulesBody from './RulesBody';

export default {
  components: {
    TheQuestion,
    RulesHeader,
    RulesBody,
  },
  methods: {
    addQuestion(question) {
      this.$emit('new-question', question)
    }
  }
};
</script>

<style>
.rules-column {
  display: grid;
  grid-template-rows: repeat(3, min-content);
  grid-row-gap: 5rem;
}
</style>
