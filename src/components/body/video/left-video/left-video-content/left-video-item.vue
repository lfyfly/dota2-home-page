<!-- —————————————↓SCSS———————分界线————————————————————————— -->
<style lang="scss">
@import 'src/scss/index.scss';

.left-video-item {
  width: 100%;
  height: 100%;
  padding: 23px 34px 0 34px;
  position: relative;


  .video-item-item {
    position: relative;


    box-sizing: border-box;
    padding: 10px;
    margin: 2px;
    border: 1px solid transparent;
    transition: border .2s, color .2s;


    &:hover {
      color: $active-color;
      border: 1px solid $active-color;
      box-shadow: 0 0 5px $active-color;

      &:after {
        position: absolute;
        content: "";
        top: 40px;
        left: 80px;
        @include bgImg(54, 54, -3, -1099, '/static/img/icons.png')
      }
    }

    &>.item-img {
      display: inline-block;
      width: 200px;

      height: 117px;
      overflow: hidden;
      position: relative;
      &:after {
        content: '视频';
        position: absolute;
        right: 0;
        bottom: 0;
        width: 35px;
        line-height: 20px;
        background: rgba(3, 4, 12, 0.8);
      }
      img {
        width: 200px;
        height: 117px;
      }
    }
    &>.item-title {
      width: 200px;
      text-align: center;
      line-height: 18px;
      margin-top: 8px;
      margin-bottom: 8px;
    }
  }
}
</style>

<!-- —————————————↓HTML————————分界线———————————————————————— -->
<template lang="pug">
//- 左侧 视频中心选项卡 的 内容容器中的子元素组件
.left-video-item.horizontal
  a.video-item-item(v-for="(v,i) in data")
    a.item-img: img(:src="v.src")
    p.item-title {{v.title}}

</template>

<!-- ——————————————↓JS—————————分界线———————————————————————— -->
<script>
//import XXX from './components/XXX'

export default {
  name: 'left-video-item',
  props: {
    data: {
      type: Array,
      required: true
    }
  },
  data() {
    return {
      msg: 'this is from left-video-item.vue'
    }
  },
  methods: {

  }
}
</script>
