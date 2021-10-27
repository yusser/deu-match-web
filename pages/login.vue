<template>
  <div id="LoginPage">
    <el-card>
      <div id="card-container">
        <div id="card-header">Para entrar clique no batão abaixo</div>
        <div>
          <a href="#" @click.prevent="Logar">
            <img
              src="~/assets/img/linkedin.png"
              width="163px"
              height="50px"
              alt="Linkedin"
            />
          </a>
        </div>
      </div>
    </el-card>
  </div>
</template>

<script>
export default {
  name: 'Login',
  layout: 'login',
  auth: false,
  methods: {
    Logar() {
      this.$auth.loginWith('linkedin')
    },
  },
}
</script>
<style lang="css" scoped>
#LoginPage {
  width: 400px;
}
#LoginPage #card-container {
  margin-top: 30px;
  margin-bottom: 30px;
  text-align: center;
}
#LoginPage #card-header {
  margin-bottom: 30px;
}
</style>
