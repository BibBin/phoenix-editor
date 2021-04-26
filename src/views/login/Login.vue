<template>
  <div class="container">
    <validate-form @form-submit="onFormSubmit">
      <div class="mb-3">
        <label class="form-label">邮箱地址</label>
        <validate-input :rules="emailRules" v-model="email" placeholder="请输入邮箱"></validate-input>
        <div>{{email}}</div>
      </div>
      <div class="mb-3">
        <label class="form-label">密码</label>
        <validate-input :rules="passwordRules" v-model="password" placeholder="请输入密码"></validate-input>
      </div>
      <template v-slot:submit>
        <span class="btn btn-primary">Submit</span>
      </template>
    </validate-form>
  </div>
</template>
<script lang="ts">
import ValidateInput, { RulesProp } from '@/components/ValidateInput/ValidateInput.vue';
import ValidateForm from '@/components/ValidateForm/ValidateForm.vue';
import { defineComponent, ref } from 'vue';
export default defineComponent({
  name: "login",
  components: {ValidateForm, ValidateInput},
  setup() {
    const email =ref('')
    const password =ref('')
    const emailRules: RulesProp = [
      {type: 'required', message: '电子邮箱不能为空'},
      {type: 'email', message: '请输入正确的电子邮箱'},
    ]
    const passwordRules: RulesProp = [
      {type: 'required', message: '密码不能为空'},
    ]
    const onFormSubmit = (result: boolean) => {
      console.log(result)
    }
    return {
      emailRules,
      passwordRules,
      email,
      password,
      onFormSubmit
    }
  }
})
</script>
<style lang="less" scoped>
.container{
 text-align: left;
 width: 300px;
 margin-top: 50px;
}
</style>