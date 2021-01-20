<template>
    <div class="column rules-column">
    <rules-header></rules-header>
    <p>Rules explained here.</p>
  </div>   
</template>

<script>
import RulesHeader from './RulesHeader';

export default {
  components: {
    RulesHeader,
  },
}
</script>

<style>
  .rules-column {
    grid-row: 2 / 3;
    grid-column: 2/3 ;
  }
</style>