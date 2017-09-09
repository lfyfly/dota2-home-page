<!-- —————————————↓SCSS———————分界线————————————————————————— -->
<style lang="scss">
@import 'src/scss/index.scss';
.right-match {
  .carousel {
    height: 314px;
    background: #161619;
    .item-img:hover .picTitle {
      color: $active-color;
    }
    .picTitle {
      cursor: pointer;


      position: absolute;
      top: 232px;

      width: 100%;

      font-size: 20px;
      color: #fff;
      line-height: 42px;
      text-align: center;
      &:hover {
        color: $active-color;
      }
    }
    .dots {
      bottom: 10px;
    }
  }
}
</style>

<!-- —————————————↓HTML————————分界线———————————————————————— -->
<template lang="pug">
//- 新闻组件的 右侧 赛事中心组件
.right-match
  icon-title(text="赛事中心")
  carousel(:imgsArr="rightMatchData",:hasPrevNext="false",)
</template>

<!-- ——————————————↓JS—————————分界线———————————————————————— -->
<script>
import iconTitle from '../icon-title.vue'
import carousel from 'src/commom/components/carousel.vue'


export default {
  name: 'right-match',
  components: {
    iconTitle,
    carousel
  },
  data() {
    return {
      msg: 'this is from right-match.vue',
      rightMatchData: [
        { src: "static/img/body/news/match-center-carousel-1.jpg", picTitle: '2017国际邀请赛中国区预选赛' },
        { src: "static/img/body/news/match-center-carousel-2.jpg", picTitle: '2017国际邀请赛中国区公开赛' },
        { src: "static/img/body/news/match-center-carousel-3.jpg", picTitle: '拯救者杯高校联赛' },
        { src: "static/img/body/news/match-center-carousel-4.jpg", picTitle: 'DOTA2亚洲邀请赛' },
      ]
    }
  },
  methods: {

  }
}
</script>
