<template>
  <div class="column rules-column">
    <rules-header></rules-header>
    <rules-body></rules-body>

  </div>
</template>

<script>
import RulesHeader from './RulesHeader';
import RulesBody from './RulesBody';

export default {
  components: {
    RulesHeader,
    RulesBody,
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
