<template>
  <component :is="type" class="title2" :class="className">
    <slot></slot>
  </component>
</template>

<script>
export default {
  name: "Title2",
  status: "prototype",
  release: "3.5.0",
  props: {
    type: {
      type: String,
      default: "h3",
    },
    className: {
      type: String,
      default: "",
    },
  },
}
</script>

<style lang="scss" scoped>
.title2 {
  font-family: var(--heading-font);
  font-weight: normal;
  font-size: 18px;
  line-height: 43px;
  text-transform: uppercase;
  color: var(--primary-text);
  margin-bottom: 0;

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
