<template>
  <div class="column rules-column">
    <rules-header></rules-header>
    <rules-body></rules-body>
    <the-question></the-question>
  </div>
</template>

<script>
import RulesHeader from './RulesHeader';
import RulesBody from './RulesBody';
import TheQuestion from './TheQuestion';

export default {
  components: {
    RulesHeader,
    RulesBody,
    TheQuestion
  },
};
</script>

<style>
.rules-column {
  display: grid;
  grid-template-rows: repeat(3, min-content);
  grid-row-gap: 5rem;
}
</style>
