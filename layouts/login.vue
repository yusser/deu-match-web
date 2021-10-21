<template>
  <div id="LoginLayout">
    <img
      id="logo-linkedin"
      src="http://www.deal.com.br/wp-content/uploads/2021/02/deal-logo.svg"
      alt="Deal"
      width="198px"
      height="69px"
    />
    <hr />
    <div id="logo-deu-match">Deu Match</div>
    <nuxt />
  </div>
</template>

<script>
export default {
  name: 'LoginLayout',
  head() {
    return {
      title: 'Deal DeuMatch - ' + this.$route.path,
    }
  },
}
</script>

<style lang="css" scoped>
#LoginLayout {
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.726);
}
#logo-linkedin {
  margin-top: 90px;
}
#logo-deu-match {
  color: white;
  font-size: 41px;
  font-weight: 800;
  margin-bottom: 50px;
}
hr {
  width: 100px;
  margin-top: 20px;
  margin-bottom: 15px;
}
</style>
