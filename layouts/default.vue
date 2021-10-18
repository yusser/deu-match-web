<template>
  <div>
    <div>Header</div>
    <div>Menu</div>
    <nuxt />
    <div>Footer</div>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: 'Deal DeuMatch - ' + this.$route.path,
    }
  },
}
</script>

<style lang="scss">
</style>
