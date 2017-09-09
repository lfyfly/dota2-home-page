<!-- —————————————↓SCSS———————分界线————————————————————————— -->
<style lang="scss">
@import 'src/scss/index.scss';

.right-map {
  margin-top: 20px;
  .map-content {
    .map-item {
      &:hover {
        img {
          border: 1px solid $active-color;
        }
        .map-title {
          color: $active-color;
        }
      }
      &:first-child {
        margin-right: 20px;
      }
      img {
        display: block;
        border: 1px solid transparent;
        box-sizing: border-box;
      }
      width: 200px;
      height: 120px;
    }
    .map-title {
      text-align: center;
      line-height: 38px;
      background: #222328;
    }
  }
}
</style>

<!-- —————————————↓HTML————————分界线———————————————————————— -->
<template lang="pug">
//- 活动中心组件 右侧的 自定义地图组件
.right-map
  icon-title(text="自定义地图")
  .map-content.horizontal
    .map-item(v-for="(v,i) in mapData")
      a.item-img: img(:src="v.src")
      .map-title {{v.title}}

</template>

<!-- ——————————————↓JS—————————分界线———————————————————————— -->
<script>
import iconTitle from '../icon-title.vue'


export default {
  name: 'right-map',
  components: {
    iconTitle
  },
  data() {
    return {
      msg: 'this is from right-map.vue',
      mapData: [
        { src: 'static/img/body/activity/self-map/self-map-0.jpg', title: '2VS2 MID VALENCE' },
        { src: 'static/img/body/activity/self-map/self-map-1.jpg', title: 'ONE PATH TO VICTORY' },
      ]
    }
  },
  methods: {

  }
}
</script>
