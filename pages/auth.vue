<template>
  <div>
    <pre style="color:white;width:50%">Usuário atenticado...</pre>
  </div>
</template>

<script>
export default {
  name: 'Auth',
  layout: 'login',
  auth: false,
  data() {
    return {
      user: null
    }
  },
  async mounted() {
    if (this.$route.query && this.$route.query.user) {
      const user = JSON.parse(window.atob(this.$route.query.user))
      await this.$auth.setUserToken('123123', '2313123')
      await this.$auth.setUser(user)
      this.$router.push('/')
    }
  }
}
</script>
