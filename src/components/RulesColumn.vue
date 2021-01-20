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
    /* display: grid; */
    /* grid-row: 1 / 2; 
    grid-column: 1/ 2 ;  */
  }
</style>