<template>
  <div class="add-idea">
    <form @submit.prevent="onSubmit">
      <label for="Next Idea"></label>
      <input :disabled="fullOfIdeas" type="text" name="newIdea" v-model="newIdea"/>
      <button :disabled='fullOfIdeas'>Add Idea</button>
    </form>
  </div>
</template>

<script>

export default {
  props: ['numOfIdeas'],
  data(){
    return {
      newIdea: ''
    }
  }, 
  methods: {
    onSubmit(){
      if (this.newIdea !== '') {
        this.$emit('add-idea', this.newIdea);
        this.newIdea = '';
      }
    }
  },
  computed: {
    fullOfIdeas() {
      return this.numOfIdeas.length === 20 ? true : false; 
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

      &[disabled] {
        background: rgba(0, 0, 0, 0.7);
      }
    }
    button[disabled] {
        background: rgba(0, 0, 0, 0.7);

    }
  }

</style>
