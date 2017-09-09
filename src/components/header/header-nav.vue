<!-- —————————————↓SCSS———————分界线————————————————————————— -->
<style lang="scss">
@import 'src/scss/index.scss';
.header-nav {
  .header-nav-item:hover {
    .title {
      color: $active-color;
    }
    background: #000;
    background: url('/static/img/header/data2.home.nav.hover.bg.png') no-repeat top center;
    background-size: cover;
  }
}
</style>

<!-- —————————————↓HTML————————分界线———————————————————————— -->
<template lang="pug">
ul.header-nav.clearfix
  header-nav-item.fl(
      v-for="(v,i) in navData",
      :data="v",
      @mouseover.native="activeIndex=i",
      @mouseout.native="activeIndex=NaN",
      :isDropdown="activeIndex===i"
    )


</template>

<!-- ——————————————↓JS—————————分界线———————————————————————— -->
<script>
import headerNavItem from './header-nav/header-nav-item.vue'


export default {
  name: 'header-nav',
  components: {
    headerNavItem
  },
  data() {
    return {
      msg: 'this is from header-nav.vue',
      activeIndex: NaN,
      navData: [
        { titleCn: '首页', titleEn: 'HOME', list: ['品牌站', '个人中心', '神秘商店', '玩家工坊'] },
        { titleCn: '资讯', titleEn: 'NEWS', list: ['官方新闻', '赛事新闻', '更新日志', '游戏攻略'] },
        { titleCn: '赛事', titleEn: 'MATCH', list: ['赛事执行', '赛事总览', '赛事活动'] },
        { titleCn: '互动', titleEn: 'INTERACTION', list: ['精粹综合', '官方活动', '玩家论坛', '新浪微博', '官方微信'] },
        { titleCn: '资料', titleEn: 'DATA', list: ['英雄资料', '物品资料', '视频中心', '自定义地图', '新手引导'] },
        { titleCn: '服务', titleEn: 'SERVICE', list: ['客服中心', '在线客服', '自助专区', '被盗找回', '忘记账号', '通行证查询', '网吧特权'] },
        { titleCn: '下载', titleEn: 'DOWN', list: ['游戏下载', '刀塔助手', '精美壁纸', '官方漫画'] },
      ]
    }
  },
  methods: {

  }
}
</script>
