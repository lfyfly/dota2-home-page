<!-- —————————————↓SCSS———————分界线————————————————————————— -->
<style lang="scss">
.layout-fixed-width {
  &>.inner {
    margin: 0 auto;
  }
}
</style>

<!-- —————————————↓HTML————————分界线———————————————————————— -->
<template lang="pug">
.layout-fixed-width
  .inner(:style="{width:width+'px'}")
    slot
</template>

<!-- ——————————————↓JS—————————分界线———————————————————————— -->
<script>
//import XXX from './components/XXX'

export default {
  name: 'layout-fixed-width',
  props: {
    width: {
      type: Number,
      default: 800
    }
  }
}
</script>
