<template>
  <component :is="type" class="title2" :class="[className, `title2--${variant}`]">
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
    variant: {
      type: String,
      default: "normal",
      validator: val => ["light", "normal", "primary"].includes(val),
    },
  },
}
</script>

<style lang="scss" scoped>
.title2 {
  font-weight: bold;
  font-size: 18px;
  line-height: 26px;
  color: var(--primary-text);
  margin-bottom: 0;

  &--light {
    color: #fff;
  }

  &--primary {
    color: var(--color-primary);
  }

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
