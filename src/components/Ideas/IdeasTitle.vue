<template>
  <div class="header__title">
    <Icon :icon="icons.light" :style="{ fontSize: '32px' }" />
    <h2 class="header__title">How can I {{question}}?</h2>
  </div>
</template>

<script>
import { Icon } from '@iconify/vue';
import lightBulb from '@iconify/icons-heroicons-outline/light-bulb';

export default {
  props: ['question'],
  components: {
    Icon,
  },
  data() {
    return {
      icons: {
        light: lightBulb,
      },
    };
  },
};
</script>

<style lang="scss" scoped>
.header__title {
  display: flex;

  h2 {
    margin-left: 2rem;
    font-weight: 400;
    margin-bottom: 2rem;
  }
}</style
>>
