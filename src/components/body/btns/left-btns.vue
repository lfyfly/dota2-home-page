<!-- —————————————↓SCSS———————分界线————————————————————————— -->
<style lang="scss">
@import 'src/scss/index.scss';

//——————————与right-btns共享——————————————
.btn .opacity-transition {
  opacity: 0;
  transition: opacity 1s;
  &:hover {
    opacity: 1;
  }
}
//——————————与right-btns共享——————————————

.left-btns {
  .btn,
  .btn .opacity-transition {

    @include bgImg0(246, 93, '/static/img/body/btns/u_left_buttons.png');
    margin-right: 6px;
  }

  .btn1 {
    .opacity-transition {
      background-position: 0 -94px;
    }
  }
  .btn2 {
    background-position: -252px 0;
    .opacity-transition {
      background-position: -252px -94px;
    }
  }
  .btn3 {
    background-position: -508px 0;
    margin-right: 0;
   .opacity-transition {
      background-position: -508px -94px;
    }
  }
}
</style>

<!-- —————————————↓HTML————————分界线———————————————————————— -->
<template lang="pug">
.left-btns
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
  name: 'left-btns',
  data() {
    return {
      msg: 'this is from left-btns.vue'
    }
  },
  methods: {

  }
}
</script>
