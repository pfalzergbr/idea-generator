<template>
    <div class="header__counter">
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

<style lang="scss" scoped>
  .header__counter {
    margin-left: 1rem;
    margin-bottom: 2rem;
    
  }

</style>