<template>
  <component :is="type" class="display3">
    <slot></slot>
  </component>
</template>

<script>
export default {
  name: "Display3",
  status: "prototype",
  release: "3.5.0",
  props: {
    type: {
      type: String,
      default: "h3",
    },
  },
}
</script>

<style lang="scss" scoped>
.display3 {
  font-family: var(--heading-font);
  font-style: normal;
  font-weight: normal;
  font-size: 32px;
  line-height: 39px;
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
