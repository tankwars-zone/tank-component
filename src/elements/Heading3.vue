<template>
  <component :is="type" class="heading3" :class="`heading3--${variant}`"><slot /></component>
</template>

<script>
export default {
  name: "Heading3",
  props: {
    type: {
      type: String,
      default: "div",
    },
    variant: {
      type: String,
      default: "normal",
    },
  },
}
</script>

<style lang="scss" scoped>
.heading3 {
  font-weight: bold;
  font-size: 24px;
  line-height: 32px;
  text-transform: uppercase;
  color: #0d123a;
  margin-bottom: 24px;

  @include mobile {
    font-size: 18px;
    line-height: 24px;
    margin-bottom: 16px;
  }

  &--light {
    color: #fff;
  }

  &--primary {
    color: var(--primary);
  }
}
</style>
