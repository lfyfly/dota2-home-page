<!-- —————————————↓SCSS———————分界线————————————————————————— -->
<style lang="scss">
.left-video-content {
  width: 750px;
  height: 430px;
  border: 1px solid #333;
  box-sizing: border-box;
}
</style>

<!-- —————————————↓HTML————————分界线———————————————————————— -->
<template lang="pug">
//- 左侧 视频中心选项卡 的 内容容器组件
.left-video-content
  left-video-item(v-for="(v,i) in videoData",:data="v",v-show="activeIndex===i")

</template>

<!-- ——————————————↓JS—————————分界线———————————————————————— -->
<script>
import leftVideoItem from './left-video-content/left-video-item.vue'

export default {
  name: 'left-video-content',
  props: {
    activeIndex: {
      type: Number,
      default: 0
    }
  },
  components: {
    leftVideoItem
  },
  data() {
    return {
      msg: 'this is from left-video-content.vue',
      videoData: [
        [
          { src: 'static/img/body/video/video-0-1.png', title: '【DOTA2】TI7地区预选赛蛋疼时刻集锦 队友都是影帝' },
          { src: 'static/img/body/video/video-0-2.jpg', title: '2017年国际邀请赛地区预选赛 最终日TOP10视频集锦' },
          { src: 'static/img/body/video/video-0-3.jpg', title: 'Dota2论演员的自我修养 第四期 超载黑车 一死三命' },
          { src: 'static/img/body/video/video-0-4.jpg', title: 'Abed预选赛个人秀：14杀2死15助暴走卡尔第一视角' },
          { src: 'static/img/body/video/video-0-5.jpg', title: 'Vega-Empire 140分钟大战 TI7预选赛最长膀胱局诞生！' },
          { src: 'static/img/body/video/video-0-6.jpg', title: '阿瑟解说：dota2破泞之战第一幕全三星大型攻略视频' },
        ],
        [
          { src: 'static/img/body/video/video-1-1.png', title: '2017国际邀请赛 中国赛区预选赛各直邀战队前瞻视频' },
          { src: 'static/img/body/video/video-1-2.jpg', title: '冠军之路永无止竞——TI7中国区预选赛即将火热开启' },
          { src: 'static/img/body/video/video-1-3.jpg', title: 'V社官方纪录片真视界基辅特锦赛篇 OG勇者与VP大魔王' },
          { src: 'static/img/body/video/video-1-4.jpg', title: 'DAC小组赛官方精彩集锦:奇迹哥卡尔秀翻全场' },
          { src: 'static/img/body/video/video-1-5.jpg', title: 'DAC小组赛前花絮视频 各队伍定妆照拍摄中' },
          { src: 'static/img/body/video/video-1-6.png', title: 'DAC周边酒店场馆介绍视频 这个真的很重要哦' },
        ],
        [
          { src: 'static/img/body/video/video-2-1.jpg', title: 'Abed预选赛个人秀：14杀2死15助暴走卡尔第一视角' },
          { src: 'static/img/body/video/video-2-2.jpg', title: 'Vega-Empire 140分钟大战 TI7预选赛最长膀胱局诞生！' },
          { src: 'static/img/body/video/video-2-3.png', title: 'BurNIng徐志雷解说TS7巅峰联赛总决赛 Secret-VP视频' },
          { src: 'static/img/body/video/video-2-4.jpg', title: 'DS7巅峰联赛胜者组第一轮：LGD 2-1 NP集锦视频' },
          { src: 'static/img/body/video/video-2-5.png', title: '莫斯科震中杯2017总决赛 Liquid 3-1 EG比赛视频' },
          { src: 'static/img/body/video/video-2-6.jpg', title: '震中杯2017总决赛开幕式视频 谜团单挑肉山 爆炸特效' },
        ],
        [
          { src: 'static/img/body/video/video-3-1.png', title: '离子解说 B神敌法师 vs OB蜀(头)山(翔)双(组)雄(合)' },
          { src: 'static/img/body/video/video-3-2.jpg', title: 'ZOTAC索泰杯大师赛总决赛 Newbee 3-1 NP比赛视频' },
          { src: 'static/img/body/video/video-3-3.jpg', title: 'SL-i国际邀请赛小组赛 Newbee 0-2 Vega比赛视频' },
          { src: 'static/img/body/video/video-3-4.png', title: 'EvilGeniuses战队基辅特锦赛纪录片 天才的日常第四集 ' },
          { src: 'static/img/body/video/video-3-5.png', title: '传说中的圣剑背0秒？老鸡杀小鸡 屠龙宝刀点击就送' },
          { src: 'static/img/body/video/video-3-6.jpg', title: '心疼VGJ被做成集锦了 VP史诗级combo黑贤拉接萨尔大' },
        ]
      ]
    }
  },
  methods: {

  }
}
</script>
