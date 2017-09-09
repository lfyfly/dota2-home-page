<!-- —————————————↓SCSS———————分界线————————————————————————— -->
<style lang="scss">
.layout-left-right {

  &>.left {
    float: left;
  }
  &>.right {
    float: right;
  }
}
</style>

<!-- —————————————↓HTML————————分界线———————————————————————— -->
<template lang="pug">
.layout-left-right.clearfix
  .left(:style="{width:leftWidth?leftWidth+'px':''}")
    slot(name="left")
  .right(:style="{width:rightWidth?rightWidth+'px':''}")
    slot(name="right")

</template>

<!-- ——————————————↓JS—————————分界线———————————————————————— -->
<script>
//import XXX from './components/XXX'

export default {
  name: 'layout-left-right',
  props: {
    leftWidth: {
      type: Number,
    },
    rightWidth: {
      type: Number,
    }
  }

}
</script>
