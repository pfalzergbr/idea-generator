<template>
  <div>
    <span>{{number}}</span>
    <span>{{idea}}</span>
  </div>
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

<style></style>
