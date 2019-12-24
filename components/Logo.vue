<template>
  <nuxt-link to="/" class="logo">
    Glenn Dutrieux
  </nuxt-link>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.logo {
  color: white;
  font-weight: bold;
  font-size: 28px;
  z-index: 10;
}

a.logo {
  &:hover {
    text-decoration: none;
  }
}
</style>
