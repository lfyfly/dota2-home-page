<!-- —————————————↓SCSS———————分界线————————————————————————— -->
<style lang="scss">
.left-activity-content {
  width: 100%;
  height: 486px;
  padding: 42px;
  border: 1px solid #333;
  box-sizing: border-box;

  position: relative;
  & .left-activity-item,
  & .left-activity-item-shop,
  {
    position: absolute;
  }
}
</style>

<!-- —————————————↓HTML————————分界线———————————————————————— -->
<template lang="pug">
//- 左侧活动中心 选项卡内容容器组件
.left-activity-content
  template(v-for="(v,i) in activityData")
    left-activity-item(v-if="i<3",:data="v",v-show="activeIndex===i")
    left-activity-item-shop(v-else,:data="v",v-show="activeIndex===3")
</template>

<!-- ——————————————↓JS—————————分界线———————————————————————— -->
<script>
import leftActivityItem from './left-activity-content/left-activity-item.vue'
import leftActivityItemShop from './left-activity-content/left-activity-item-shop.vue'

export default {
  name: 'left-activity-content',
  components:{
    leftActivityItem,
    leftActivityItemShop
  },
  props:{
    activeIndex:{
      type:Number,
      default:0
    }
  },
  data() {
    return {
      msg: 'this is from left-activity-content.vue',
      activityData: [
        [
          { title: '助力TI7本土启航战 神秘商店限时特卖开启', imgSrc: 'static/img/body/activity/activity-tab-1-1.jpg', state: '进行中' },
          { title: 'DOTA2风行敌法手办现货发送', imgSrc: 'static/img/body/activity/activity-tab-1-2.jpg', state: '已结束' },
          { title: '周末特惠 — 勇士等级珍藏礼包', imgSrc: 'static/img/body/activity/activity-tab-1-3.png', state: '已结束' },
          { title: '破泞之战推出 黄沙Roshan等你开启', imgSrc: 'static/img/body/activity/activity-tab-1-4.jpg', state: '进行中' }
        ],
        [
          { title: '2017国际邀请赛预选赛线上观战', imgSrc: 'static/img/body/activity/activity-tab-2-1.jpg' },
          { title: '2017国际邀请赛中国区公开赛报名', imgSrc: 'static/img/body/activity/activity-tab-2-2.jpg' },
          { title: '2017国际邀请赛受邀战队公布', imgSrc: 'static/img/body/activity/activity-tab-2-3.jpg' },
          { title: '基辅特级锦标赛激情开战', imgSrc: 'static/img/body/activity/activity-tab-2-4.jpg' },
        ],
        [
          { title: '贴吧电竞：秀出你的DOTA2战绩', imgSrc: 'static/img/body/activity/activity-tab-3-1.png' },
          { title: '联想拯救者DAC官方指定用机', imgSrc: 'static/img/body/activity/activity-tab-3-2.jpg' },
          { title: '京东游戏玩家惠', imgSrc: 'static/img/body/activity/activity-tab-3-3.jpg' },
          { title: '维他可可助力DOTA2亚洲邀请赛', imgSrc: 'static/img/body/activity/activity-tab-3-4.jpg' },
        ],
        [
          { title: '2017年国际邀请赛勇士令状', logo: '近期热点', price: 6000, info: '满溢着任务、宝藏和奖励，2017年国际邀请赛勇士令状是Dota夏季的绝佳陪伴。', imgSrc: 'static/img/body/activity/activity-tab-4-1.jpg' },
          { title: '2017年国际邀请赛典藏宝瓶', logo: '特色珍藏', price: 1200, info: '工具', imgSrc: 'static/img/body/activity/activity-tab-4-2.png' },
        ]
      ]
    }
  },
  methods: {

  }
}
</script>
