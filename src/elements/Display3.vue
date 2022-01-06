<template>
  <component :is="type" class="display3" :class="[className, `display3--${variant}`]">
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
.display3 {
  font-family: var(--heading-font);
  font-style: normal;
  font-weight: normal;
  font-size: 32px;
  line-height: 39px;
  text-transform: uppercase;
  color: var(--primary-text);
  margin-bottom: 24px;

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
