<!-- —————————————↓SCSS———————分界线————————————————————————— -->
<style lang="scss">
@import 'src/scss/index.scss';

.right-btns {
    height: 95px;
    .btn,
    .btn .opacity-transition {
      @include bgImg0(140, 95, '/static/img/body/btns/u_right_buttons.png');
    }
    .btn1 {
      .opacity-transition {
        background-position: 0 -96px;
      }
    }
    .btn2 {
      background-position: -140px 0;
      .opacity-transition {
        background-position: -140px -96px;
      }
    }
    .btn3 {
      background-position: -280px 0;
      .opacity-transition {
        background-position: -280px -96px;
      }
    }
}
</style>

<!-- —————————————↓HTML————————分界线———————————————————————— -->
<template lang="pug">
.right-btns
  a.btn.btn1
    span.opacity-transition
  a.btn.btn2
    span.opacity-transition
  a.btn.btn3
    span.opacity-transition

</template>

<!-- ——————————————↓JS—————————分界线———————————————————————— -->
<script>
//import XXX from './components/XXX'

export default {
  name: 'right-btns',
  data() {
    return {
      msg: 'this is from right-btns.vue'
    }
  },
  methods: {

  }
}
</script>
