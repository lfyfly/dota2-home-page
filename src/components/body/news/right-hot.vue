<!-- —————————————↓SCSS———————分界线————————————————————————— -->
<style lang="scss">
  @import 'src/scss/index.scss';
.right-hot {
  .video {
    width: 420px;
    height: 202px;
    overflow: hidden;
    position: relative;

    video {
      width: 420px;
      background-color: #15242c;
    }
    .video-title {
      @include bgImg0(420,202,'/static/img/body/news/video_bg.png');
      position: absolute;
      left: 0;
      top: 0;
      img {
        position: absolute;
        left: 50%;
        margin-left: -125px;
        bottom: 8px;
      }
    }
  }
}
</style>

<!-- —————————————↓HTML————————分界线———————————————————————— -->
<template lang="pug">
//- 新闻组件的右侧 近期热点组件
.right-hot
  icon-title(text="近期热点", :hasmore="false")
  .video
    video(style="height: 269px;margin-top: -57px;", preload="preload", muted="true", autoplay="", autobuffer="true", loop="loop", poster="static/img/body/news/video-poster.jpg")
      source(type="video/mp4", src="static/img/body/news/right-vedio-1.mp4")
      source(type="video/webm", src="static/img/body/news/right-vedio-1.mp4.webm")

    img(src="static/img/body/news/right-video-img-1.jpg")
    a.video-title
      h1.video-title-text
        img(src="static/img/body/news/video-text.png")
</template>

<!-- ——————————————↓JS—————————分界线———————————————————————— -->
<script>
import iconTitle from '../icon-title.vue'


export default {
  name: 'right-hot',
  components: {
    iconTitle
  },
  data() {
    return {
      msg: 'this is from right-hot.vue'
    }
  },
  methods: {

  }
}
</script>
