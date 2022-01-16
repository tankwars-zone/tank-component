<template>
  <div class="overline" :class="`overline--${variant}`">
    <slot />
  </div>
</template>

<script>
export default {
  name: "Overline",
  props: {
    variant: {
      type: String,
      default: "normal",
      // validator: (val) => ['light', 'normal', 'primary'].includes(val),
    },
  },
}
</script>

<style lang="scss" scoped>
.overline {
  font-weight: 600;
  font-size: 24px;
  line-height: 31px;
  text-transform: uppercase;
  color: var(--text-primary);

  &--light {
    color: #fff;
  }

  &--primary {
    color: var(--primary);
  }

  @include mobile {
    font-weight: 600;
    font-size: 16px;
    line-height: 20px;
  }
}
</style>
