<template>
  <component :is="type" class="title1" :class="[className, `title1--${variant}`]">
    <slot></slot>
  </component>
</template>

<script>
export default {
  name: "Title1",
  status: "prototype",
  release: "3.5.0",
  props: {
    type: {
      type: String,
      default: "h4",
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
.title1 {
  font-family: var(--heading-font);
  font-weight: bold;
  font-size: 24px;
  line-height: 32px;
  color: var(--primary-text);
  margin-bottom: 8px;

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
