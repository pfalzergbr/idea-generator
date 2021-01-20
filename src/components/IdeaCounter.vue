<template>
    <div>
      <p>{{numOfIdeas}} items on the list, {{ideasLeft}} more to go!</p>
    </div>
</template>

<script>
export default {
  props: ['numOfIdeas'],
  computed: {
    ideasLeft() {
      return 20 - this.numOfIdeas;
    }
  }
}
</script>

<style>

</style>