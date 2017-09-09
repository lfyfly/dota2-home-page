<!-- —————————————↓SCSS———————分界线————————————————————————— -->
<style lang="scss">
.left-news {}
</style>

<!-- —————————————↓HTML————————分界线———————————————————————— -->
<template lang="pug">
//- 左侧新闻组件
.left-news
  icon-title(text="新闻中心")
  repeat-nav(:data="newsNavData",@switch='switchFn')
  left-news-content(:activeIndex = "activeIndex")
</template>

<!-- ——————————————↓JS—————————分界线———————————————————————— -->
<script>
import iconTitle from '../icon-title.vue'
import repeatNav from '../repeat-nav.vue'
import leftNewsContent from './left-news/left-news-content.vue'

export default {
  name: 'left-news',
  components: {
    iconTitle,
    repeatNav,
    leftNewsContent,
  },
  data() {
    return {
      msg: 'this is from left-news.vue',
      activeIndex: 0,
      newsNavData: [{ text: '综合新闻' }, { text: '官方新闻' }, { text: '赛事新闻' }, { text: '更新日志' }, { text: '媒体资讯' }],

    }
  },
  methods: {
    switchFn(activeIndex) {
      this.activeIndex = activeIndex
    }
  }
}
</script>
