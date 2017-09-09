<!-- —————————————↓SCSS———————分界线————————————————————————— -->
<style lang="scss">
.left-activity {
  height: 534px;

  position: relative;
  .title-container {
    position: relative;
    height: 45px;
    width: 100%;
    position: absolute;
  }
  .left-activity-nav {
    right: 0;
    bottom: 0;
  }
}
</style>

<!-- —————————————↓HTML————————分界线———————————————————————— -->
<template lang="pug">
//- 左侧 活动中心组件
.left-activity
  .title-container
    icon-title(text="活动中心",:hasmore="false")
    left-activity-nav(@switch="switchFn")
    left-activity-content(:activeIndex="activeIndex")
</template>

<!-- ——————————————↓JS—————————分界线———————————————————————— -->
<script>
import iconTitle from '../icon-title.vue'
import leftActivityNav from './left-activity/left-activity-nav.vue'
import leftActivityContent from './left-activity/left-activity-content.vue'

export default {
  name: 'left-activity',
  components: {
    iconTitle,
    leftActivityNav,
    leftActivityContent
  },
  data() {
    return {
      msg: 'this is from left-activity.vue',
      activeIndex:0
    }
  },
  methods: {
    switchFn(activeIndex) {
      this.activeIndex = activeIndex
    }
  }
}
</script>
