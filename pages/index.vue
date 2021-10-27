<template>
  <div>
    <h1>Teste</h1>
    <div>Teste 2</div>
    <button @click="Sair">Sair</button>
  </div>
</template>

<script>
export default {
  methods: {
    async Sair() {
      await this.$auth.logout()
      this.$router.push('/login')
    }
  }
}
</script>
