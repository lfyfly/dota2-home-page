<!-- —————————————↓SCSS———————分界线————————————————————————— -->
<style lang="scss">
.repeat-nav {
@import 'src/scss/index.scss';
  &>li {
    cursor: pointer;
    position: relative;

    box-sizing: border-box;

    line-height: 36px;
    text-align: center;
    border: 1px solid #333;
    border-right: 1px solid transparent;
    &:last-child {
      border-right: 1px solid #333;
    }

    &:hover,
    &.active {
      border: 1px solid #999;
      color: #ccc;
      position: relative;
      z-index: 1;
      transition: border .5s;
    }

    .hot{
      position: absolute;
      top:1px;
      right:18px;
    }
  }
}
</style>

<!-- —————————————↓HTML————————分界线———————————————————————— -->
<template lang="pug">
//- 相同样式的 选项卡导航组件
//- 活动中心组件（left-activety.vue）调用
//- 视频中心组件（left-video.vue）调用
ul.repeat-nav.horizontal
  li(v-for="(v,i) in data",
    :class="{active: activeIndex===i}",
    :style="{width:100/data.length +'%'}",
    @click="activeIndex=i"
  ) {{v.text}}
    .hot.hot-icon(v-if="v.isHot")


</template>

<!-- ——————————————↓JS—————————分界线———————————————————————— -->
<script>
//import XXX from './components/XXX'

export default {
  name: 'repeat-nav',
  props: {
    data: {
      type: Array,
      required: true
    }
  },
  data() {
    return {
      msg: 'this is from repeat-tab.vue',
      activeIndex: 0
    }
  },
 watch:{
   activeIndex(){
     this.$emit('switch',this.activeIndex)
   }
 }
}
</script>
