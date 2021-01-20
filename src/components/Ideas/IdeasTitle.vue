<template>
  <div class="header">
    <Icon :icon="icons.light" :style="{ fontSize: '32px' }" />
    <h2 class="header__title">Header</h2>
  </div>
</template>

<script>
import { Icon } from '@iconify/vue';
import lightBulb from '@iconify/icons-heroicons-outline/light-bulb';

export default {
  props: [],
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
.header {
  display: flex;

  &__title {
    margin-left: 2rem;

  }
}</style
>>
