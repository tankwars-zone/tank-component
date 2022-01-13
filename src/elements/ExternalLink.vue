<template>
  <a :href="href" target="_blank" rel="noopener noreferrer" class="external-link">
    <slot />
  </a>
</template>

<script>
export default {
  name: "External",
  props: {
    href: {
      type: String,
      default: "",
    },
  },
}
</script>

<style lang="scss" scoped>
.external-link {
  color: var(--primary);
  text-decoration: none;
  font-weight: bold;
}
</style>
