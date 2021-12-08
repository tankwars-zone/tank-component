<template>
  <div class="subline">
    <slot></slot>
  </div>
</template>

<style lang="scss" scoped>
.subline {
  font-size: 20px;
  line-height: 40px;
  color: var(--secondary);
  margin-bottom: 40px;

  @include iPadPro {
    font-size: 16px;
    line-height: 30px;
  }
}
</style>
