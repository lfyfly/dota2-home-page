<!-- —————————————↓SCSS———————分界线————————————————————————— -->
<style lang="scss">
.left-video {}
</style>

<!-- —————————————↓HTML————————分界线———————————————————————— -->
<template lang="pug">
//- 左侧 视频中心组件
.left-video
  icon-title(text="视频中心")
  repeat-nav(:data="videoNav",@switch="switchFn")
  left-video-content(:activeIndex="activeIndex")
</template>

<!-- ——————————————↓JS—————————分界线———————————————————————— -->
<script>
import iconTitle from '../icon-title.vue'
import repeatNav from '../repeat-nav.vue'
import leftVideoContent from './left-video/left-video-content.vue'


export default {
  name: 'left-video',
  components: {
    iconTitle,
    repeatNav,
    leftVideoContent
  },
  data() {
    return {
      msg: 'this is from left-video.vue',
      activeIndex: 0,
      videoNav: [{ text: '最新视频' }, { text: '官方视频 ', isHot: true }, { text: '比赛视频', isHot: true }, { text: '战队视频' }],

    }
  },
  methods: {
    switchFn(activeIndex) {
      this.activeIndex = activeIndex
    }
  }
}
</script>
