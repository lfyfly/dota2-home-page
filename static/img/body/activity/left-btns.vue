<!-- —————————————↓SCSS———————分界线————————————————————————— -->
<style lang="scss">
.left-btns {
  .btn,
  .btn .opacity-transition {
    cursor: pointer;

    display: inline-block;
    width: 246px;
    height: 93px;
    background: url('/static/img/body/btns/u_left_buttons.png') no-repeat;
    margin-right: 6px;
  }
  .btn .opacity-transition {
    opacity: 0;
    transition: opacity 1s;
    &:hover {
      opacity: 1;
    }
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
