<!-- —————————————↓SCSS———————分界线————————————————————————— -->
<style lang="scss">
.right-update {
  .right-update-carousel {
    margin-top: 20px;
    padding-top: 30px;

  }
}
</style>

<!-- —————————————↓HTML————————分界线———————————————————————— -->
<template lang="pug">
//- 活动中心组件 右侧的 版本更新组件
.right-update
  icon-title(text="版本更新")
  carousel-3d.right-update-carousel(:imgsArr="updateData",:imgWidth="230",:height="224",:width="420")
</template>

<!-- ——————————————↓JS—————————分界线———————————————————————— -->
<script>
import iconTitle from '../icon-title.vue'
import carousel3d from 'src/commom/components/carousel-3d.vue'


export default {
  name: 'right-update',
  components: {
    iconTitle,
    carousel3d
  },
  data() {
    return {
      msg: 'this is from right-update.vue',
      updateData: [
        { src: "static/img/body/activity/carousel-update/carousel-3d-0.jpg", title: '7.02游戏性能更新' },
        { src: "static/img/body/activity/carousel-update/carousel-3d-1.jpg", title: '7.03"剑心之遗"版本更新' },
        { src: "static/img/body/activity/carousel-update/carousel-3d-2.jpg", title: '7.04游戏性能更新' },
        { src: "static/img/body/activity/carousel-update/carousel-3d-3.jpg", title: '7.05游戏性能更新' },
        { src: "static/img/body/activity/carousel-update/carousel-3d-4.jpg", title: '7.06游戏性能更新' },
      ]
    }
  },
  methods: {

  }
}
</script>
