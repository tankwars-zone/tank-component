<template>
  <h2 class="display1">
    <slot></slot>
  </h2>
</template>

<style lang="scss" scoped>
.display1 {
  font-family: var(--heading-font);
  font-style: normal;
  font-weight: normal;
  font-size: 48px;
  line-height: 58px;
  text-transform: uppercase;
  color: var(--primary-text);
  margin-bottom: 40px;

  @include iPadPro {
    font-size: 36px;
    line-height: 43px;
    margin-bottom: 25px;
  }

  @include mobile {
    font-size: 34px;
    line-height: 44px;
    margin-bottom: 30px;
  }
}
</style>
