<!-- —————————————↓SCSS———————分界线————————————————————————— -->
<style lang="scss">
@import 'src/scss/index.scss';
.right-service {

  .service-container {
    box-sizing: border-box;
    width: 420px;
    height: 470px;
    background: #15161a;
    padding: 20px 20px 0 20px;
  } // ___________search-bar_________
  .search-bar {
    &>* {
      box-sizing: border-box;
      vertical-align: middle;
      height: 35px;
    }
    &>.search-input {
      border: 1px solid #000;
      background: #111214;
      width: 244px;
      outline: none;
      color: #999;
      text-indent: 10px;
    }

    &>.search-btn {
      border-radius: 4px;
      background-color: $active-color-1;
      &:hover {
        background-color: #f76161;
      }
    }
    .ask-question-btn {
      width: 90px;
      color: #ccc;

      background-color: #565864;
      border-radius: 2px;
      margin-left: 10px;
      line-height: 35px;
      text-align: center;
      &:hover {
        background-color: #6a6c77;
      }
    }
  } //___________questions___________
  .questions {
    margin-top: 26px;

    .questions-title {
      display: inline-block;
      width: 380px;
      padding-bottom: 10px;
      font-size: 16px;
      color: #ccc;
      border-bottom: 1px solid #333;
    }
    .questions-list {
      margin-top: 18px;
      .questions-item {
        &:first-child a {
          color: $active-color-1;
          .dot-icon {
            background-position: -3px -825px;
          }
        }
        .questions-item-a {

          &:hover {
            color: $active-color;
            .dot-icon {
              background-position: -3px -814px;
            }
          }
          line-height: 36px;
          color: #ccc;
          .questions-text {
            display: inline-block;
            vertical-align: middle;
          }
        }
      }
    }
  }
}
</style>

<!-- —————————————↓HTML————————分界线———————————————————————— -->
<template lang="pug">
//- 左侧视频中心组件 右侧的 客服执行组件
.right-service
  icon-title(text="客服中心")
  .service-container
    .search-bar.horizontal
      input.search-input(placeholder="请输入您的问题")
      a.search-btn.search-icon
      a.ask-question-btn 我要提问

    .questions
      a.questions-title 常见问题
      ul.questions-list
        li.questions-item(v-for="v in questionsData")
          a.questions-item-a
            i.dot-icon
            p.questions-text {{v}}

</template>

<!-- ——————————————↓JS—————————分界线———————————————————————— -->
<script>
import iconTitle from '../icon-title.vue'

export default {
  name: 'right-service',
  components: {
    iconTitle
  },
  data() {
    return {
      msg: 'this is from right-service.vue',
      questionsData: [
        '如何找回与DOTA2账户绑定的完美通行证？',
        '为什么我需要注册两个账号？',
        '如何注册DOTA2账号？',
        '如何绑定完美通行证（完美电竞账号）？',
        '运行游戏后显示“正在连接到DOTA2网络”, 怎么办？',
        '进入客户端后【运行DOTA2】按钮无法点击，怎么办？',
        '更新时下载速度很慢或卡住不动，怎么办？',
        '在XP系统下切换容易使游戏导致崩溃，怎么办？',
        '如何查看自己的数字ID？',
      ]
    }
  },
  methods: {

  }
}
</script>
