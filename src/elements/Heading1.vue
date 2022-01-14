<template>
  <component :is="type" class="heading" :class="`heading--${variant}`"><slot /></component>
</template>

<script>
export default {
  name: "Heading1",
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
.heading {
  font-weight: bold;
  font-size: 56px;
  line-height: 71px;
  text-transform: uppercase;
  color: var(--text-primary);

  &--light {
    color: #fff;
  }

  &--primary {
    color: var(--primary);
  }

  @include iPadPro {
    font-size: 38px;
    line-height: 44px;
  }

  @include mobile {
    font-size: 32px;
    line-height: 41px;
  }
}
</style>
