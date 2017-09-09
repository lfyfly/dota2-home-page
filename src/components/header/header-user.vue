<!-- —————————————↓SCSS———————分界线————————————————————————— -->
<style lang="scss">
@import 'src/scss/index.scss';

.header-user {
  height: 50px;
  margin: 15px;
  .header-user-avtar-icon {
    background-color: #101215;
    border-radius: 50%;
    border: 1px solid #262323;
  }
  .user-login {
    margin-left: 15px;
    line-height: 24px;
    .login-text {
      font-size: 18px;

      a {
        color: $active-color;
        &:hover {
          text-decoration: underline;
        }
      }
    }
    .login-tip {
      font-size: 12px;
      line-height: 17px;
    }
  }
}
</style>

<!-- —————————————↓HTML————————分界线———————————————————————— -->
<template lang="pug">
.header-user.horizontal.icon-text-hor
  .header-user-avtar-icon
  .user-login
    p.login-text 您好，请&nbsp;
      a 登录
    p.login-tip 登录后可进入您的个人中心
</template>

<!-- ——————————————↓JS—————————分界线———————————————————————— -->
<script>
//import XXX from './components/XXX'

export default {
  name: 'header-user',
  data() {
    return {
      msg: 'this is from header-user.vue'
    }
  },
  methods: {

  }
}
</script>
