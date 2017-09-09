<!-- —————————————↓SCSS———————分界线————————————————————————— -->
<style lang="scss">
@import 'src/scss/index.scss';
.my-footer {
    font-size: 12px;
    padding: 40px 0;
    background: #000;
    margin-top: 120px;
   .footer-left, .footer-right{
     display: inline-block;
   }
  .wanmei-logo {
    margin-right: 40px;
    vertical-align: top;
  }
  .valve-logo{
    margin-right: 20px;
  }
  .wanmei-info{
    vertical-align: top;
    padding-top: 2px;
  }
  .row1{
    margin-bottom: 20px;
  }
  .row2{
    width: 614px;
    color: #333;
    line-height: 16px;
  }
}
</style>

<!-- —————————————↓HTML————————分界线———————————————————————— -->
<template lang="pug">
layoutFixedWidth.my-footer(:width="890")
  a.footer-left.wanmei-logo
  .footer-right
    .row1.horizontal
      a.valve-logo
      .wanmei-info
        | 完美世界（北京）网络技术有限公司 版权所有 Copyright © 2012-2017 Perfect World Co., Ltd. All Rights reserved
        br
        | ©2012 Valve Corporation. All Rights reserved. Licensed to Perfect World Co., Ltd. in China
    .row2.records-info
        | 京ICP证：050016号《网络文化经营许可证》编号：京网文[2011]0782-287号 《网络视听许可证》编号：0110587
        br
        | 京公网安备110105019888号 文网进字[2013] 028号 新出审字[2013] 1505号 ISBN：978-7-89989-826-0
</template>

<!-- ——————————————↓JS—————————分界线———————————————————————— -->
<script>
import layoutFixedWidth from 'src/commom/components/layout/layout-fixed-width.vue'

export default {
  name: 'my-footer',
  data() {
    return {
      msg: 'this is from my-footer.vue'
    }
  },
  components: {
    layoutFixedWidth
  },
  methods: {

  }
}
</script>
