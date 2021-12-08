<template>
  <h2 class="display2">
    <slot></slot>
  </h2>
</template>

<style lang="scss" scoped>
.display2 {
  font-family: var(--heading-font);
  font-style: normal;
  font-weight: normal;
  font-size: 36px;
  line-height: 43px;
  text-align: center;
  text-transform: uppercase;
  color: var(--primary-text);
  margin-bottom: 24px;

  @include tablet {
    font-size: 24px;
    line-height: 30px;
  }

  @include mobile {
    font-size: 24px;
    line-height: 32px;
    margin-bottom: 30px;
  }
}
</style>
