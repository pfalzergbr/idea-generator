<template>
  <li>
    <span>{{number}}. </span>
    <span>{{idea}}</span>
  </li>
</template>

<script>
export default {
  props: ['idea', 'index'],
  computed: {
    number() {
      return this.index + 1 
    }
  }
};
</script>

<style lang="scss" scoped>
  li {
    list-style: none;
    padding: .25rem;
    font-size: 1.2rem;
  }
  
</style>
