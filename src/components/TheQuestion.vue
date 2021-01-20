<template>
  <div class="the-question">
    <div class="the-question__container">
      <h2 class="the-question__question">How can I...</h2>
      <textarea v-model.trim="question"></textarea>
      <button class="the-question__btn" @click="submitQuestion">Start</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      question: '',
      error: null
    };
  },
  methods: {
    submitQuestion() {
      this.error = null;
      if (this.question) {
        this.$emit('newQuestion', this.question);
      } else {
        this.error = 'You need to ask first...'
      }
    },
  },
};
</script>

<style lang="scss" scoped>
.the-question {
  display: flex;

  // &__btn {
  //   background: #F7D1A8;
  //   font-size: 1.6rem;
  //   text-transform: uppercase;
  //   transition: all .2s;

  // &:hover , &:focus {
  //   background: #ec9432;
  // }
  // }

  &__question {
    margin-bottom: 2rem;
  }
  &__container {
    display: flex;
    flex-direction: column;
    width: 100%;

    textarea {
      margin-bottom: 2rem;
      padding: 1rem;
    }
  }
}
</style>
