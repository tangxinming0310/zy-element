<template>
  <LgForm class="form" ref="form" :model="user" :rules="rules">
    <LgFormItem label="用户名" prop="username">
      <LgInput v-model="user.username" placeholder="请输入用户名"></LgInput>
    </LgFormItem>
    <LgFormItem label="密码" prop="password">
      <LgInput type="password" v-model="user.password"></LgInput>
    </LgFormItem>
    <LgFormItem prop="username">
      <LgButton type="primary" @click="login">登录</LgButton>
    </LgFormItem>
  </LgForm>
</template>

<script>
import LgForm from './form/Form.vue'
import LgFormItem from './form/FormItem.vue'
import LgInput from './form/Input.vue'
import LgButton from './form/LgButton.vue'
export default {
  name: 'Login',
  components: {
    LgForm,
    LgButton,
    LgFormItem,
    LgInput
  },
  data () {
    return {
      user: {
        username: '',
        password: ''
      },
      rules: {
        username: [{
          required: true,
          message: '请输入用户名'
        }],
        password: [{
          required: true,
          message: '请输入密码'
        }]
      }
    }
  },
  methods: {
    login() {
      this.$refs.form.validate((valid) => {
        if (valid) {
          alert('success')
        } else {
          alert('failed')
        }
      })
      console.log('click')
    }
  }
}
</script>

<style>

</style>