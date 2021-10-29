<template>
  <div id="Perfil">
    <div id="Menu">
      <h3 class="active">Perfil</h3>
      <h3>Habilidades</h3>
      <h3>Vagas</h3>
    </div>
    <div id="Content">
      <div>
        Perfil do Candidato:
        <hr />
        <img :src="image" alt="profileImage">
        <pre>
          {{ user }}
        </pre>
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
  width: 210px;
}

#Content {
  background-color: white;
  height: 100%;
  width: 100%;
  border-radius: 0 0 0 20px;
}
#Content div {
  padding:25px;
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
