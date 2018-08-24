<template>
  <div id="app">
    <el-form ref="form" :model="form" :rules="validationRules" status-icon>
      <el-form-item label="An input:" prop="field">
        <el-input class="input" v-model="form.field"/>          
      </el-form-item>
    </el-form>
  </div>
</template>

<script>
const validationRules = {
	field: [{ validator: (rule, value, callback) => {
    callback()
  } }],
}

export default {
	name: 'app',

	data() {
		return {
			form: { field: 'some-very-very-veryvery-very-ver-long-string' },
			validationRules,
		}
  },
  
  mounted() {
    this.$refs.form.validate()
  }
}
</script>

<style scoped>
.input {
  width: 200px;
}
</style>
