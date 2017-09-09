<!-- —————————————↓SCSS———————分界线————————————————————————— -->
<style lang="scss">
@import 'src/scss/index.scss';

.left-activity-nav {
  position: absolute;

  &>li {
    cursor: pointer;

    width: 140px;
    text-align: center;
    border-bottom: 1px solid transparent;
    box-sizing: border-box;
    height: 40px;
    &:hover,
    &.active {
      border-bottom: 1px solid $active-color;
    }
    &:last-child a {
      border-right: none;
    }
    a {
      position: relative;

      display: inline-block;
      width: 100%;

      line-height: 20px;
      border-right: 1px solid $base-font-color;
    }

    &:hover a,
    &.active a {
      color: $active-color;
    }

    .hot {
      position: absolute;
      top: -8px;
      right: 2px;
    }
  }
}
</style>

<!-- —————————————↓HTML————————分界线———————————————————————— -->
<template lang="pug">
//- 左侧活动中心 选项卡导航组件
ul.left-activity-nav.horizontal
  li(v-for="(v,i) in activityNav",@mouseover="activeIndex=i",:class="{active:activeIndex===i}")
    a {{v.text}}
      .hot.hot-icon(v-if="v.isHot")

</template>

<!-- ——————————————↓JS—————————分界线———————————————————————— -->
<script>
//import XXX from './components/XXX'

export default {
  name: 'left-activity-nav',
  data() {
    return {
      msg: 'this is from left-activity-nav.vue',
      activeIndex: 0,
      activityNav: [{ text: '官方活动' }, { text: '赛事活动', isHot: true }, { text: '商城特选' }, { text: '商城特选' }],

    }
  },
  methods: {

  },
  watch: {
    activeIndex() {
      this.$emit('switch', this.activeIndex)
    }
  }
}
</script>
