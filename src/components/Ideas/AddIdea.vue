<template>
  <div class="add-idea">
    <form @submit.prevent="onSubmit">
      <label for="Next Idea"></label>
      <input type="text" name="newIdea" v-model="newIdea"/>
      <button>Add Idea</button>
    </form>
  </div>
</template>

<script>

export default {
  data(){
    return {
      newIdea: ''
    }
  }, 
  methods: {
    onSubmit(){
      this.$emit('add-idea', this.newIdea);
    }
  }
};
</script>

<style lang="scss" scoped>
  form {
    display: flex;
    width: 100%;
      margin-bottom: 2rem;
    input {
      flex: 1 ;
    }
  }

</style>
