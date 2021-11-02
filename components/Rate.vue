<template>
  <div class="Rate">
    <div class="label">{{ name }}</div>
    <el-rate
      v-model="value"
      :texts="['Júnior', 'Pleno', 'Sênior']"
      show-text
      :max="3"
    >
    </el-rate>
  </div>
</template>

<script>
export default {
  name: 'Rate',
  props: {
    name: {
      type: String,
      require: true,
      default: 'Skill',
    },
  },
  data() {
    return {
      value: null,
    }
  },
}
</script>

<style>
.Rate .label {
  padding-top: 10px;
  padding-bottom: 10px;
}
</style>
