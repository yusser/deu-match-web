<template>
  <div id="Perfil">
    <div id="Menu">
      <h3 class="active">Perfil</h3>
      <h3>Habilidades</h3>
      <h3>Vagas</h3>
    </div>
    <div id="Content">
      <div class="padding-25">
        <div class="header">Complete o cadastro com dados pessoais...</div>
        <img :src="image" alt="profileImage">
        {{ user.id }}
        {{ user.localizedFirstName }}
        {{ user.localizedLastName }}
        {{ user.emailAddress }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Perfil',
  data() {
    return {
      user: {},
      image: null
    }
  },
  mounted() {
    this.user = JSON.parse(JSON.stringify(this.$auth.user))
    this.image = this.user.profilePicture.Image800
    delete this.user.profilePicture
  }
}
</script>

<style>
#Perfil {
  display: flex;
  height: 100%;
}

#Menu {
  width: 180px;
}

#Content {
  background-color: white;
  height: calc(100%-220px);
  width: calc(100% - 180px);
  border-radius: 0 0 0 20px;
}
#Content div.padding-25 {
  padding:0 25px 0 25px;
}
#Content .header {
  color: #464646;
  font-weight: 600;
  font-size: 1.17em;
  padding-top: 21px;
  padding-bottom: 18px;
  margin-bottom: 25px;
  border-bottom: 1px dotted #464646;
}

h3 {
  color: white;
  cursor: pointer;
  margin: 0;
  padding-top: 20px;
  padding-bottom: 20px;
  padding-left: 20px;
  border-radius: 20px 0 0 20px;
}

h3.active, h3:hover {
  background-color: white;
  color: #464646;
}
</style>
