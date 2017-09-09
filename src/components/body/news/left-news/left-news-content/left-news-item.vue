<!-- —————————————↓SCSS———————分界线————————————————————————— -->
<style lang="scss">
.left-news-item {

  width: 750px;
  color: #999;
  position: absolute;

  .first-news {
    cursor: pointer;
    margin: 0 5px 15px 5px;
    padding: 15px 40px 15px 20px;
    border: 1px solid transparent;
    &:hover {
      border: 1px solid #00c0ff;
      box-shadow: 0 0 8px #00c0ff;
    }
    .first-news-title {
      font-size: 24px;
      line-height: 1;
      color: #00c0ff;
      margin-bottom: 22px;
    }
    .first-news-content {
      overflow: hidden;
      &>* {
        float: left;
      }
    }
    .first-news-img {
      width: 200px;
      height: 120px;
      margin-right: 20px;
    }
    .first-news-summary {
      line-height: 1.6;
      width: 458px;
      .date {
        margin-top: 10px;
        font-size: 12px;
      }
    }
  }
  .other-news-title {
    cursor: pointer;
    padding: 0 40px 0 20px;
    box-sizing: border-box;
    font-size: 16px;
    font-weight: normal;
    color: #ccc;
    line-height: 45px;
    height: 45px;
    vertical-align: middle;
    &:nth-child(odd) {
      background: #18191c;
    }
    &:hover {
      color: #00c0ff;
      & .dot-icon {
        background-position: -3px -814px;
      }
    }

    .date {
      float: right;
      font-size: 12px;
    }
  }
}
</style>

<!-- —————————————↓HTML————————分界线———————————————————————— -->
<template lang="pug">
//- 选项卡内容容器中 单个子元素组件
.left-news-item
    template(v-for="(v,i) in data")
      .first-news(v-if="i===0")
        h2.first-news-title {{v.title}}
        .first-news-content
          img.first-news-img(:src="v.imgSrc")
          .first-news-summary
            p {{v.summary}}
            p.date {{v.date}}
      h3.other-news-title(v-if="i>0")
        i.dot-icon
        span.text {{v.title}}
        span.date {{v.date}}

</template>

<!-- ——————————————↓JS—————————分界线———————————————————————— -->
<script>
//import XXX from './components/XXX'

export default {
  name: 'left-news-item',
  props: {
    data: {
      type: Array,
      required: true
    }
  },
  data() {
    return {
      msg: 'this is from left-news-item.vue'
    }
  },
  methods: {

  }
}
</script>
