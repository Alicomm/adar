<template>
  <button class="calculator-button">
    <slot />
    <calculator-icon class="calculator-button-icon" />
  </button>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';

import CalculatorIcon from '@/assets/img/calculator/signs.svg?inline';

@Component({
  components: {
    CalculatorIcon,
  },
})
export default class CalculatorButton extends Vue {}
</script>

<style lang="scss" scoped>
.calculator-button {
  display: inline-flex;
  align-items: center;
  color: var(--s-color-theme-accent);
  cursor: pointer;
  background: var(--s-color-utility-body);
  border: none;
  border-radius: calc(var(--s-border-radius-mini) / 2);
  font-size: var(--s-font-size-mini);
  font-weight: 400;
  line-height: var(--s-line-height-medium);
  padding: $inner-spacing-tiny $inner-spacing-mini;
  text-transform: uppercase;

  &-icon > path {
    fill: var(--s-color-theme-accent);
  }

  & > span + &-icon {
    margin-left: $inner-spacing-tiny;
  }
}
</style>
