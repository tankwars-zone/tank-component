<template>
  <component :is="type" class="heading2" :class="`heading2--${variant}`"><slot /></component>
</template>

<script>
export default {
  name: "Heading2",
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
.heading2 {
  font-weight: bold;
  font-size: 36px;
  line-height: 32px;
  text-transform: uppercase;
  color: var(--text-primary);
  margin-bottom: 24px;

  @include iPadPro {
    font-size: 26px;
    line-height: 28px;
  }

  &--light {
    color: #fff;
  }

  &--primary {
    color: var(--primary);
  }
}
</style>
