<template>
  <div id="DefaultLayout">
    <el-container>
      <el-header height="70px">
        <div id="logo">
          <img
            id="logo-deal"
            src="http://www.deal.com.br/wp-content/uploads/2021/02/deal-logo.svg"
            alt="Deal"
            height="50px"
          />
          <span id="logo-deu-match">Deu Match</span>
        </div>
        <div>
          <el-button @click="Sair">Sair</el-button>
        </div>
      </el-header>
      <el-main><nuxt /></el-main>
      <el-footer height="90px">
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
  background-color: #464646;
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
  font-size: 41px;
  font-weight: 800;
  margin-left: 30px;
}
#DefaultLayout .el-main {
  padding-bottom: 0;
}
#DefaultLayout .el-footer {
  display: flex;
  align-items: center;
  justify-content: center;
  margin-left: 180px;
}
</style>
