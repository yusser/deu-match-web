<template>
  <div id="DefaultLayout">
    <el-container>
      <el-header height="70px">
        <div id="logo">
          <img
            id="logo-deal"
            src="http://www.deal.com.br/wp-content/uploads/2021/02/deal-logo.svg"
            alt="Deal"
            width="198px"
            height="69px"
          />
          <span id="logo-deu-match">Deu Match</span>
        </div>
        <div>
          <button @click="Sair">Sair</button>
        </div>
      </el-header>
      <el-main><nuxt /></el-main>
      <el-footer>
        <span style="color: rgba(255, 255, 255, 0.39)">
          Deal 2021 © All rights Reserved. Designed by Deal 💚
        </span>
      </el-footer>
    </el-container>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: 'Deal DeuMatch - ' + this.$route.path,
    }
  },
  methods: {
    async Sair() {
      await this.$auth.logout()
      this.$router.push('/login')
    },
  },
}
</script>

<style lang="css">
#DefaultLayout {
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.726);
}
#DefaultLayout .el-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-top: 15px;
}
#DefaultLayout .el-header #logo {
  display: flex;
  align-items: center;
}
#DefaultLayout .el-header #logo img {
  padding-right: 35px;
  border-right: 1px solid white;
}
#DefaultLayout .el-header #logo #logo-deu-match{
  color: white;
  font-size: 50px;
  font-weight: 800;
  margin-left: 30px;
}
#DefaultLayout .el-footer {
  display: flex;
  justify-content: center;
}
</style>
