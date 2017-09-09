<!-- —————————————↓SCSS———————分界线————————————————————————— -->
<style lang="scss">
@import 'src/scss/index.scss';

.left-activity-item-shop {

  width: 668px;
  height: 444px;
  position: relative;
  .shop-item-item {
    width: 300px;
    height: 376px;
    position: relative;

    vertical-align: top;
    &:first-child {
      padding-right: 31px;
      border-right: 1px solid #333;
    }
    &:nth-child(2) {
      margin-left: 32px;
    }
    .item-item-img {
      width: 300px;
      height: 200px;
    }
    .title {
      font-size: 16px;
      margin-top: 23px;
      color: $body-font-color-lighter;
    }
    .price {
      color: #a93827;
      margin-top: 8px;
      font-size: 16px;
    }
    .info {
      height: 24px;
      margin-top: 24px;
      color: #666;
      margin-bottom: 20px;
    }
    .shop-logo {
      position: absolute;
      top: 1px;
      left: 1px;

      width: 102px;
      height: 33px;

      background: url('/static/img/body/activity/shop.png') no-repeat;
      &.logo2 {
        background-position: 2px -66px;
      }
    }
    .shop-btn {
      height: 43px;
      width: 100%;
      font-size: 18px;
      color: #d3cbc7;
      line-height: 43px;
      text-align: center;
      cursor: pointer;
      background: url('/static/img/body/activity/activities-shop-btn.jpg') 0px -43px no-repeat;
      &:hover {
        background-position: 0 0;
        color: #fff;
      }
    }
  }
}
</style>

<!-- —————————————↓HTML————————分界线———————————————————————— -->
<template lang="pug">
//- 左侧活动中心 选项卡内容子元素组件（第四个）
.left-activity-item-shop.horizontal
  .shop-item-item(v-for="(v,i) in data")
    a.a-img: img.item-item-img(:src="v.imgSrc")
    p.title {{v.title}}
    p.price {{v.price}}刀币
    p.info {{v.info}}

    .shop-logo(:class="{logo1:v.logo==='近期热点',logo2:v.logo==='特色珍藏'}")
    .shop-btn 立即购买
  .activity-more
</template>

<!-- ——————————————↓JS—————————分界线———————————————————————— -->
<script>
//import XXX from './components/XXX'

export default {
  name: 'left-activity-item-shop',
  props: {
    data: {
      type: Array,
      required: true
    }
  },
  data() {
    return {
      msg: 'this is from left-activity-item-shop.vue'
    }
  },
  methods: {

  }
}
</script>
