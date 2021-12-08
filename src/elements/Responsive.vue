<template>
  <div>
    <div class="desktop">
      <slot name="desktop"></slot>
    </div>
    <div class="ipad">
      <slot name="ipad"></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: "Responsive",
  status: "prototype",
  release: "3.5.0",
}
</script>

<style scoped lang="scss">
.desktop {
  display: block;

  @include iPadPro {
    display: none;
  }
}

.ipad {
  display: none;

  @include iPadPro {
    display: block;
  }
}
</style>
