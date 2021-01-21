<template>
  <li>
    <span class="number">{{number}}. </span>
    <span class="idea">{{idea}}</span>
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

    .number {
      margin-right: 1rem;
    }
  }


  
</style>
