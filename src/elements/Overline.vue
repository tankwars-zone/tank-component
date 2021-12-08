<template>
  <h3 class="overline">
    <slot></slot>
  </h3>
</template>

<style lang="scss" scoped>
.overline {
  font-family: var(--heading-font);
  font-style: normal;
  font-weight: normal;
  font-size: 24px;
  line-height: 29px;
  text-transform: uppercase;
  color: var(--primary);
  margin-top: 0;
  margin-bottom: 4px;

  @include iPadPro {
    font-size: 18px;
    line-height: 22px;
  }

  @include mobile {
    font-size: 18px;
    line-height: 22px;
  }
}
</style>
