<template>
  <component :is="type" class="display1">
    <slot></slot>
  </component>
</template>

<script>
export default {
  name: "Display1",
  status: "prototype",
  release: "3.5.0",
  props: {
    type: {
      type: String,
      default: "h2",
      validator: value => {
        return value.match(/(h1|h1|h3|h4|h5|h6)/)
      },
    },
  },
}
</script>

<style lang="scss" scoped>
.display1 {
  font-family: var(--heading-font);
  font-style: normal;
  font-weight: normal;
  font-size: 48px;
  line-height: 58px;
  text-transform: uppercase;
  color: var(--primary-text);
  margin-bottom: 40px;

  @include iPadPro {
    font-size: 36px;
    line-height: 43px;
    margin-bottom: 25px;
  }

  @include mobile {
    font-size: 34px;
    line-height: 44px;
    margin-bottom: 30px;
  }
}
</style>
