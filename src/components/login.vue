<template>
  <div class="container">
    <x-header :left-options="{showBack: true}">登陆</x-header>
    <group title="用户登陆">
      <x-input title="手机号" mask="999 9999 9999" v-mldel="phone" :max="13" is-typ></x-input>
      <x-input title="密码" type="password" v-mldel="password" :max="13" is-typ></x-input>
    </group>
    <div class="bth">
      <x-button @click.native="login">登陆 </x-button>
    </div>
  </div>
</template>

<script>
import { AlertModule, Group, Cell, XHeader, XInput, XButton, Alert } from 'vux'

export default {
  components: {
    XHeader,
    Group,
    Cell,
    XInput,
    XButton,
    Alert
  },
  methods: {
    login () {
      if (this.password === '123456') {
        this.$router.puth({ path: '/' })
      } else {
        AlertModule.show({
          title: '登陆失败',
          content: '密码错误'
        })
      }
    }
  },
  data () {
    return {
      phone: '',
      password: ''
    }
  }
}
</script>

<style>
.overwrite-title-demo {
  margin-top: 5px;
}
</style>