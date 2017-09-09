<!-- —————————————↓SCSS———————分界线————————————————————————— -->
<style lang="scss">
@import 'src/scss/index.scss';
.left-activity-item {
  position: relative;
  width: 668px;
  height: 444px;
  .activity-item-item {
    position: relative;
    &:first-child,
    &:nth-child(3) {
      margin-right: 40px;
    }

    .title {
      font-size: 16px;
      margin-top: 12px;
      margin-bottom: 34px;
    }
    .item-item-img {
      width: 310px;
      height: 150px;
      border: 1px solid #000;
      &:hover {
        border: 1px solid $active-color;
      }
    }
    .state {
      position: absolute;
      z-index: 1;
      top: 0;
      left: 0;
      width: 60px;
      line-height: 24px;
      text-align: center;

      &.valid {
        background: rgba(114, 202, 42, 0.7);
        color: #fff;
      }
      &.invalid {
        background: rgba(102, 102, 102, 0.7);
      }
    }
  }

}
 .activity-more {
    width: 114px;
    height: 28px;
    background: url('/static/img/body/activity/more-bg.png') no-repeat;
    display: inline-block;
    position: absolute;
    left: 50%;
    margin-left: -59px;
    bottom: 0px;
    &:hover {
      background-position: 0 -28px;
    }
  }
</style>

<!-- —————————————↓HTML————————分界线———————————————————————— -->
<template lang="pug">
//- 左侧活动中心 选项卡内容子元素组件（前三个）
.left-activity-item.clearfix
  .activity-item-item.fl(v-for="(v,i) in data")
    a
      img.item-item-img(:src="v.imgSrc")
      .title: a  {{v.title}}
      .state(v-if="v.state",:class="{valid:v.state==='进行中',invalid:v.state==='已结束'}") {{v.state}}
  a.activity-more
</template>

<!-- ——————————————↓JS—————————分界线———————————————————————— -->
<script>
//import XXX from './components/XXX'

export default {
  name: 'left-activity-item',
  props: {
    data: {
      type: Array,
      required: true
    }
  },
  data() {
    return {
      msg: 'this is from left-activity-item.vue'
    }
  },
  methods: {

  }
}
</script>
