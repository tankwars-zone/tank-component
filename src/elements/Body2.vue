<template>
  <component :is="type" :class="['body2', className]">
    <slot></slot>
  </component>
</template>

<script>
export default {
  name: "Body2",
  status: "prototype",
  release: "3.5.0",
  props: {
    type: {
      type: String,
      default: "div",
    },
    className: {
      type: String,
      default: "",
    },
  },
}
</script>

<style lang="scss" scoped>
.body2 {
  font-weight: normal;
  font-size: 13px;
  line-height: 18px;
  color: var(--primary-text);
  margin-bottom: 0;
}
</style>
