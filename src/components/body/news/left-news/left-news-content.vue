<!-- —————————————↓SCSS———————分界线————————————————————————— -->
<style lang="scss">
.left-news-content {
  height: 528px;
  margin-top: 25px;
  position: relative;
  &>* {
    position: absolute;
  }
}
</style>

<!-- —————————————↓HTML————————分界线———————————————————————— -->
<template lang="pug">
//-左侧新闻 选项卡内容容器 组件
.left-news-content
  left-news-item(v-for="(v,i) in newsTabdata",:data="v.newsList",v-show="activeIndex===i")


</template>

<!-- ——————————————↓JS—————————分界线———————————————————————— -->
<script>
import leftNewsItem from './left-news-content/left-news-item.vue'

export default {
  name: 'left-news-content',
  props:{
    activeIndex: {
      type:Number,
      default:0
    }
  },
  components: {
    leftNewsItem,
  },
  data() {
    return {
      msg: 'this is from left-news-content.vue',
      newsTabdata: [
        {
          title: '综合新闻',
          newsList: [
            { title: 'DOTA2 7月1日更新：昆卡与潮汐猎人播音包', imgSrc: 'static/img/body/news/news1-1.jpg', date: '2017-07-01', summary: '今天的更新带来的是全新的《昆卡与潮汐猎人播音包》，为所有勇士令状超过75级的玩家开放领取。由海上的统帅和潜伏的海怪共同演绎，播音包可以将默认播音员和连杀配音替换为这对总是在拆对方台的宿敌。' },
            { title: '​2017年DOTA2国际邀请赛线下观战活动开启申请', date: '2017-06-30' },
            { title: '​LGD拿下最后门票 12支TI7地区预选赛优胜战队出炉', date: '2017-06-29' },
            { title: 'LFY斩获中国区预选赛第二个晋级名额 剩余3支战队明日背水一战', date: '2017-06-29' },
            { title: '【全球电竞网推荐】TI7中国区预选赛次日一图流 LGD双雄携手晋级淘汰赛', date: '2017-06-29' },
            { title: 'iG.V率先进入西雅图 中国区预选赛进入淘汰赛阶段', date: '2017-06-29' },
            { title: '助力TI7本土启航战 神秘商店夏季限时特卖开启', date: '2017-06-28' },
            { title: 'TI7中国区预选赛首日：iG.V、LGD、CDEC暂居积分榜第一', date: '2017-06-27' }
          ]
        },
        {
          title: '官方新闻',
          newsList: [
            { title: 'DOTA2 7月1日更新：昆卡与潮汐猎人播音包', imgSrc: 'static/img/body/news/news1-1.jpg', date: '2017-07-01', summary: '今天的更新带来的是全新的《昆卡与潮汐猎人播音包》，为所有勇士令状超过75级的玩家开放领取。由海上的统帅和潜伏的海怪共同演绎，播音包可以将默认播音员和连杀配音替换为这对总是在拆对方台的宿敌。' },
            { title: '​2017年DOTA2国际邀请赛线下观战活动开启申请', date: '2017-06-29' },
            { title: '【全球电竞网推荐】TI7中国区预选赛次日一图流 LGD双雄携手晋级淘汰赛', date: '2017-06-29' },
            { title: '​LGD拿下最后门票 12支TI7地区预选赛优胜战队出炉', date: '2017-06-29' },
            { title: 'iG.V率先进入西雅图 中国区预选赛进入淘汰赛阶段', date: '2017-06-29' },
            { title: 'TI7中国区预选赛首日：iG.V、LGD、CDEC暂居积分榜第一', date: '2017-06-29' },
            { title: '助力TI7本土启航战 神秘商店夏季限时特卖开启', date: '2017-06-28' },
            { title: '2017 MDL国际精英邀请赛VIP门票上线！惊喜福利接踵而至！', date: '2017-06-27' },
          ]
        },
        {
          title: '赛事新闻',
          newsList: [
            { title: '​2017年DOTA2国际邀请赛线下观战活动开启申请', imgSrc: 'static/img/body/news/news1-3.jpg', date: '2017-07-01', summary: '全球所有的DOTA2玩家都将目光汇聚到8月8-13日在美国西雅图开启的2017年国际邀请赛（简称TI7）主赛事。届时，远在太平洋彼岸的西雅图将迎来全世界最顶尖的DOTA2选手、最激情的解说和最热情的玩家。' },
            { title: '​LGD拿下最后门票 12支TI7地区预选赛优胜战队出炉', date: '2017-06-29' },
            { title: 'LFY斩获中国区预选赛第二个晋级名额 剩余3支战队明日背水一战', date: '2017-06-29' },
            { title: 'iG.V率先进入西雅图 中国区预选赛进入淘汰赛阶段', date: '2017-06-29' },
            { title: '助力TI7本土启航战 神秘商店夏季限时特卖开启', date: '2017-06-28' },
            { title: 'TI7中国区预选赛首日：iG.V、LGD、CDEC暂居积分榜第一', date: '2017-06-27' },
            { title: '​MAX战队斩获最后晋级名额  TI7中国区预选赛明日开启', date: '2017-06-26' },
            { title: 'MAX战队斩获最后晋级名额  TI7中国区预选赛明日开启', date: '2017-06-26' }
          ]
        },
        {
          title: '更新日志',
          newsList: [
            { title: 'DOTA2 7月1日更新：昆卡与潮汐猎人播音包', imgSrc: 'static/img/body/news/news1-1.jpg', date: '2017-07-01', summary: '今天的更新带来的是全新的《昆卡与潮汐猎人播音包》，为所有勇士令状超过75级的玩家开放领取。由海上的统帅和潜伏的海怪共同演绎，播音包可以将默认播音员和连杀配音替换为这对总是在拆对方台的宿敌。' },
            { title: '​DOTA2 6月12日更新：7.06d平衡性改动', date: '2017-06-12' },
            { title: 'DOTA2 6月1日更新日志：更改指令处理方式', date: '2017-06-01' },
            { title: 'DOTA2 5月29日更新日志：7.06c平衡性更新', date: '2017-05-29' },
            { title: '5月22日更新日志：7.06b平衡性更新', date: '2017-05-22' },
            { title: '5月15日更新日志：7.06游戏性更新', date: '2017-05-16' },
            { title: '一双手好像不够？ 2017国际邀请赛勇士令状已更新', date: '2017-05-05' },
            { title: '4月10日更新日志：7.05游戏性更新', date: '2017-04-10' },
          ]
        },
        {
          title: '媒体资讯',
          newsList: [
            { title: '【电竞虎推荐】预选赛大杀器——四号位船长分析', imgSrc: 'static/img/body/news/news1-5.jpg', date: '2017-07-01', summary: 'TI7中国区预选赛正在火热进行中，有一个英雄的BP率和胜率都十分惊人，那就是今天我们文章的主角——海军上将昆卡。' },
            { title: '【电竞虎推荐】新的中单王者？魔武双修的秀逗魔导师', date: '2017-06-27' },
            { title: '【电竞虎推荐】无情的上分机器——重回巅峰的圣堂刺客', date: '2017-06-21' },
            { title: '【易竞技】对话：10年！DOTA第一人Vigoss回来了', date: '2017-06-16' },
            { title: '【电竞虎推荐】为梦而战！TI7中国区预选赛出线形势分析', date: '2017-06-15' },
            { title: '【电竞虎推荐】痛苦是你最好的老师！——物理流女王出装打法教学', date: '2017-06-13' },
            { title: '【电竞虎推荐】火魂冲刺！——灰烬之灵中单对线详解', date: '2017-06-05' },
            { title: '【电竞虎推荐】拿好阵容赢一半——马尼拉决赛BP分析（上篇', date: '2017-06-02' },
          ]
        },
      ]
    }
  },
  methods: {

  }
}
</script>
