<template>
  <nuxt />
</template>

<script>
export default {
  head() {
    return {
      htmlAttrs: {
        class: 'dm-login-page'
      },
      title: 'Deal DeuMatch - ' + this.$route.path
    }
  }
}
</script>

<style lang="scss">
</style>
