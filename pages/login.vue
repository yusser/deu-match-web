<template>
  <div id="LoginPage">
    <el-card>
      <div id="card-container">
        <div id="card-header">Para entrar clique no batão abaixo</div>
        <div>
          <a href="#" @click.prevent="logar">
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
  async mounted() {
    if (this.$route.query && this.$route.query.code) {
      try {
        const headers = new Headers({ 'Content-Type': 'x-www-form-urlencoded' })
        const formData = new FormData()
        console.log(this.$route.query.code)
        formData.append('code', this.$route.query.code)
        formData.append('client_id', '781bflw9ulh6v1')
        formData.append('client_secret', 'JdOQ8GhmdnMBekzP')
        formData.append('redirect_uri', 'http://localhost:3000')
        formData.append('grant_type', 'authorization_code')
        const response = await fetch(
          'https://www.linkedin.com/oauth/v2/accessToken',
          {
            method: 'post',
            headers,
            body: formData,
          }
        )
        console.log(response)
      } catch (error) {
        console.log(error)
      }
    }
  },
  methods: {
    logar() {
      this.$auth
        .loginWith('linkedin')
        .then(() => this.$toast.success('Logged In!'))
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
