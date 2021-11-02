<template>
  <div id="Perfil">
    <div id="Menu">
      <h3 class="active">Perfil</h3>
      <h3>Vagas</h3>
    </div>
    <div id="Content">
      <div class="padding-25">
        <div class="header">Complete seu cadastro com dados pessoais...</div>
        <div class="content">
          <div class="aside">
            <img :src="image" alt="profileImage" />
            <div
              style="
                color: #606266;
                margin-top: 10px;
                text-align: center;
                margin-left: -10px;
              "
            >
              # {{ user.id }}
            </div>
          </div>
          <div class="dados">
            <el-form :label-position="'top'" :model="user">
              <el-form-item label="Nome">
                <el-input v-model="user.nome"></el-input>
              </el-form-item>
              <el-form-item label="E-mail">
                <el-input v-model="user.email"></el-input>
              </el-form-item>
              <label class="el-form-item__label">Habilidades</label>
              <div v-if="user.skills.length" style="display:flex;justify-content:flex-start;flex-wrap:wrap;">
                <div
                  v-for="(language, index) in optionsSkills.languages"
                  :key="index"
                  style="margin-bottom:25px;color:#606266;width:25%;"
                >
                  <div class="label">{{ language }}</div>
                  <el-rate
                    v-model="user.skills[index].level"
                    :texts="['Júnior', 'Pleno', 'Sênior']"
                    show-text
                    :max="3"
                    style="display: inline;"
                  >
                  </el-rate>
                  <div v-if="user.skills[index].level" style="float:right;margin-right:30px;padding-top:2px;cursor:pointer;" @click="user.skills[index].level=0">
                    <i class="el-icon-delete"></i>
                  </div>
                </div>
              </div>
              <el-form-item>
                <el-button @click="Salvar">Salvar</el-button>
              </el-form-item>
            </el-form>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Perfil',
  data() {
    return {
      user: {
        id: null,
        nome: null,
        email: null,
        skills: [],
      },
      image: null,
      optionsSkills: {
        languages: [
          'JavaScript',
          'SQL',
          'Java',
          'Ruby',
          'PHP',
          'Python',
          'C',
          'C++',
          'C#',
          'HTML',
          'CSS',
          'Dart',
        ],
      },
    }
  },
  mounted() {
    const user = JSON.parse(JSON.stringify(this.$auth.user))
    this.user.id = user.id
    this.user.nome = user.localizedFirstName + ' ' + user.localizedLastName
    this.user.email = user.emailAddress
    this.image = user.profilePicture.Image800
    this.user.skills = this.optionsSkills.languages.map(skill => {
      return {
        name: skill,
        level: 0
      }
    })
  },
  methods: {
    Salvar() {
      window.alert('Em desenvolvimento...')
    },
  },
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
  padding: 0 25px 0 25px;
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
#Content .content {
  display: flex;
}
#Content .content .aside img {
  border-radius: 25px;
}
#Content .content .dados {
  margin-left: 25px;
  width: calc(100% - 192px);
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
h3.active,
h3:hover {
  background-color: white;
  color: #464646;
}
</style>
