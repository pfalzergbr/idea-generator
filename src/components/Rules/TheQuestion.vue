<template>
  <div class="the-question">
    <div class="the-question__container">
      <h2 class="the-question__question">How can I...</h2>
      <textarea v-model.trim="question"></textarea>
      <button class="the-question__btn" @click="submitQuestion">Start</button>
      <p v-if="error" class="error">{{ error }}</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      question: '',
      error: null,
    };
  },
  methods: {
    submitQuestion() {
      this.error = null;
      if (this.question) {
        this.$emit('new-question', this.question);
      } else {
        this.error = 'Please type in your question first';
      }
    },
  },
};
</script>

<style lang="scss" scoped>
.the-question {
  display: flex;

  &__btn {
    margin-bottom: 1.5rem;
  }

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
  .error {
    color: red;
  }
}
</style>
