<!-- —————————————↓SCSS———————分界线————————————————————————— -->
<style lang="scss">
@import 'src/scss/index.scss';


.header-nav-item {
  width: 92px;
  height: 80px;
  position: relative;
  text-align: center;
  .titleCn {
    font-size: 16px;
  }
  .titleEn {
    font-size: 12px;
    transform: scale(0.75);
    line-height: 16px;
    margin-top: 2px;
  } // 下拉列表
  .header-nav-item-list {
    position: absolute;
    top: 100%;
    left: 0;
    z-index: 9;

    width: 100%;
    height: 240px;

    background: url('/static/img/header/level2.nav.bg.png') no-repeat;
    background-size: cover;
    color: #827c79;
    li {
      font-size: 15px;
      line-height: 2;
      &>a:hover {
        color: $active-color;
      }
    }
  }
}
</style>

<!-- —————————————↓HTML————————分界线———————————————————————— -->
<template lang="pug">
li.header-nav-item.vertical-center
  a.title
    h2.titleCn {{data.titleCn}}
    h2.titleEn {{data.titleEn}}

  ul.header-nav-item-list(v-show="isDropdown")
    li(v-for="v in data.list"): a {{v}}
</template>

<!-- ——————————————↓JS—————————分界线———————————————————————— -->
<script>
//import XXX from './components/XXX'

export default {
  name: 'header-nav-item',
  props: {
    data: {
      type: Object,
      required: true
    },
    isDropdown:{ // 是否显示下拉列表
      type: Boolean,
      default:false
    }
  },
  data() {
    return {
      msg: 'this is from header-nav-item.vue'
    }
  },
  methods: {

  }
}
</script>
