<!-- —————————————↓SCSS———————分界线————————————————————————— -->
<style lang="scss">
.my-header {
  height: 80px;
  font-size: 16px;
  background: url('/static/img/header/dota2.home.nav.bg.png') no-repeat;
  .header-logo-icon{
    display: inline-block;
    margin: 20px 20px 0 0;
  }
}
</style>

<!-- —————————————↓HTML————————分界线———————————————————————— -->
<template lang="pug">
layoutFixedWidth(:width="1200").my-header
  layoutLeftRight
    .header-left(slot="left")
      .header-logo-icon.fl
      header-nav.fl
    .header-right(slot="right")
      headerUser
</template>

<!-- ——————————————↓JS—————————分界线———————————————————————— -->
<script>
import layoutFixedWidth from 'src/commom/components/layout/layout-fixed-width.vue'
import layoutLeftRight from 'src/commom/components/layout/layout-left-right.vue'

import headerNav from 'components/header/header-nav.vue'
import headerUser from 'components/header/header-user.vue'
export default {
  name: 'my-header',
  components: {
    layoutFixedWidth,
    layoutLeftRight,

    headerNav,
    headerUser
  },
  data() {
    return {
      msg: 'this is from my-header.vue'
    }
  },
  methods: {

  }
}
</script>
