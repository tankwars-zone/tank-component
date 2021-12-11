<template>
  <component :is="type" class="title3">
    <slot></slot>
  </component>
</template>

<script>
export default {
  name: "Title3",
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
.title3 {
  font-family: var(--heading-font);
  font-weight: normal;
  font-size: 16px;
  line-height: 16px;
  text-transform: uppercase;
  color: var(--primary-text);
  margin-bottom: 0;
}
</style>
