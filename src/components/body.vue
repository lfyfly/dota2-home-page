<!-- —————————————↓SCSS———————分界线————————————————————————— -->
<style lang="scss">
.my-body {
  .layout-left-right {
    margin-bottom: 50px;
  }
  .main-carousel{
    height: 600px;
    min-width: 1200px;
  }
  .right-hot{
    margin-bottom: 28px;
  }
}
</style>

<!-- —————————————↓HTML————————分界线———————————————————————— -->
<template lang="pug">
.my-body
  carousel.main-carousel(:imgsArr="mainCarouselData")
  layoutFixedWidth(:width="1200")
    layoutLeftRight.body-btns(:leftWidth="750",:rightWidth="420")
      left-btns(slot="left")
      right-btns(slot="right")

    layoutLeftRight.body-news(:leftWidth="750",:rightWidth="420")
      left-news(slot="left")
      .right-news(slot="right")
        right-hot
        right-match

    layoutLeftRight.body-activity(:leftWidth="750",:rightWidth="420")
      left-activity(slot="left")
      .right-activity(slot="right")
        right-update
        right-map
    layoutLeftRight.body-video(:leftWidth="750",:rightWidth="420")
      left-video(slot="left")
      right-service(slot="right")

</template>

<!-- ——————————————↓JS—————————分界线———————————————————————— -->
<script>
import layoutFixedWidth from 'src/commom/components/layout/layout-fixed-width.vue'
import layoutLeftRight from 'src/commom/components/layout/layout-left-right.vue'
import carousel from 'src/commom/components/carousel.vue'

import leftBtns from 'components/body/btns/left-btns.vue'
import rightBtns from 'components/body/btns/right-btns.vue'

import leftNews from 'components/body/news/left-news.vue'
import rightHot from 'components/body/news/right-hot.vue'
import rightMatch from 'components/body/news/right-match.vue'

import leftActivity from 'components/body/activity/left-activity.vue'
import rightUpdate from 'components/body/activity/right-update.vue'
import rightMap from 'components/body/activity/right-map.vue'

import leftVideo from 'components/body/video/left-video.vue'
import rightService from 'components/body/video/right-service.vue'



export default {
  name: 'my-body',
  components: {
    layoutFixedWidth,
    layoutLeftRight,
    carousel,

    leftBtns,
    rightBtns,

    leftNews,
    rightHot,
    rightMatch,

    leftActivity,
    rightUpdate,
    rightMap,

    leftVideo,
    rightService,
  },
  data() {
    return {
      msg: 'this is from my-body.vue',
      mainCarouselData: [
        { src: "static/img/body/main-carousel/main-carousel-0.jpg" },
        { src: "static/img/body/main-carousel/main-carousel-1.jpg" },
        { src: "static/img/body/main-carousel/main-carousel-2.jpg" },
        { src: "static/img/body/main-carousel/main-carousel-3.jpg" }
      ]
    }
  },
  methods: {

  }
}
</script>
