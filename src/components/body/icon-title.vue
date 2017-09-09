<!-- —————————————↓SCSS———————分界线————————————————————————— -->
<style lang="scss">
@import 'src/scss/index.scss';

.icon-title {
  line-height: 1;
  height: 35px;
  font-size: 18px;
  margin-bottom: 10px;
  color: #fff;

  .title {
    display: inline-block;
    margin-left: 4px;

    line-height: 35px;
    font-size: 18px;
  }

  .news-center-icon {
    @include icon(-3, -1);
  }
  .recent-hot-pots-icon {
    @include icon(-40, -1);
  }
  .match-center-icon {
    @include icon(-3, -127);
  }
  .activity-center-icon {
    @include icon(-3, -85);
  }

  .version-updating-icon {
    @include icon(-3, -127);
  }
  .self-map-icon {
    @include icon(-3, -169);
  }

  .video-center-icon {
    @include icon(-3, -212);
  }
  .call-center-icon {
    @include icon(-3, -253);
  }
  .more {
    float: right;
    font-size: 12px;
    color: #999;
    margin-top: 10px;
    &:hover {
      color: $active-color;
    }
    &:hover .more-icon {
      background-position: -3px -774px;
    }
    .more-icon {
      @include bgImg(10, 10, -3, -787, '/static/img/icons.png');
      margin-left: 4px;
    }
  }
}
</style>

<!-- —————————————↓HTML————————分界线———————————————————————— -->
<template lang="pug">
//- icon和标题组合组件
//- 在 body.vue 组件中多次调用
.icon-title.icon-text-hor
  i.icon(:class="newsIconClass")
  h3.title {{text}}
  a.more.icon-text-hor(v-if="hasmore")
    span.more-text 更多
    i.more-icon

</template>

<!-- ——————————————↓JS—————————分界线———————————————————————— -->
<script>
//import XXX from './components/XXX'

export default {
  name: 'icon-title',
  props: {
    text: {
      type: String,
      default: '自定义标题'
    },
    hasmore: {
      type: Boolean,
      default: true
    }
  },
  data() {
    return {
      msg: 'this is from icon-title.vue'
    }
  },
  computed: {
    newsIconClass() {
      switch (this.text) {
        case '新闻中心':
          return 'news-center-icon'
        case '近期热点':
          return 'recent-hot-pots-icon'
        case '赛事中心':
          return 'match-center-icon'
        case '活动中心':
          return 'activity-center-icon'
        case '版本更新':
          return 'version-updating-icon'
        case '自定义地图':
          return 'self-map-icon'
        case '视频中心':
          return 'video-center-icon'
        case '客服中心':
          return 'call-center-icon'
      }
    }
  },
  methods: {

  }
}
</script>
