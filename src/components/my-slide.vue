<!-- —————————————↓SCSS———————分界线————————————————————————— -->
<style lang="scss">
@import 'src/scss/index.scss';
.my-slide {
  position: fixed;
  z-index: 9999;
  top: 50%;
  right: 0;
  margin-top: -206px;
  width: 135px;
  height: 412px;
  background: #2c3437;
  font-size: 16px;
  text-align: center;

  transition: right 1s;
  a.btn {
    box-sizing: border-box;
    width: 27px;
    height: 68px;
    background: #ac3c26;
    position: absolute;
    right: 100%;
    color: #fff;
    padding-top: 10px;
    span {
      display: block;
    }
    .close-icon {
      font-size: 19px;
    }
  }

  .online-service,
  .sina-weibo {
    background: url('/static/img/slide/bg-rightbar-box.png') repeat-x;
    border-bottom: 1px solid #47494d;
    box-sizing: border-box;
    font-size: 12px;
  }
  .online-customer-service:hover {
    background: #3f4a4e;
    .service-icon {
      background-position: -8px -53px;
    }
  }
  .sina-weibo-container:hover {
    background: #3f4a4e;
    .weibo-icon {
      background-position: -42px -51px;
    }
  }
  .online-customer-service,
  .sina-weibo-container,
  {
    text-align: center;
    display: block;
    margin-top: 16px;
    box-sizing: border-box;
    width: 90px;
    line-height: 30px;
    margin-left: 22px;
    border: 1px solid #525e63;
    color: #fff;

    .service-text {
      vertical-align: middle;
    }
  }


  .online-service {
    overflow: hidden;
    height: 95px;


    .e-mail {
      .e-mail-text {
        line-height: 24px;
      }
      .e-mail-address {
        @include bgImg(135,
        19,
        0,
        0,
        '/static/img/slide/pwrd_email.png');
      }
    }
  }

  .sina-weibo {
    height: 180px;
    overflow: hidden;

    .weixing-text {
      line-height: 30px;
    }
    .weixing-2d-code {
      @include bgImg0(90, 90, '/static/img/slide/icon-sina-qr.png');
      background-size: 90px 90px;
    }
  }
  .dota-aide {
    margin-top: -1px;
    @include bgImg0(135, 139, '/static/img/slide/img-dota2app-qr-new.png');

    &:hover {
      background-position: -135px 1px;
    }
  }
}
</style>

<!-- —————————————↓HTML————————分界线———————————————————————— -->
<template lang="pug">
.my-slide(:style="{right: isOpen? 0: '-135px'}")
  a.btn(@click="isOpen=!isOpen")
    span {{isOpen?'收起>':'展开<'}}
  .online-service
    a.online-customer-service.horizontal
      .service-icon
      .text 在线客服

    .e-mail
      .e-mail-text 投诉邮箱
      .e-mail-address
  .sina-weibo
    a.sina-weibo-container.horizontal
      .weibo-icon
      .text 新浪微博
    p.weixing-text DOTA2官方微信
    p.weixing-2d-code

  a.dota-aide


</template>

<!-- ——————————————↓JS—————————分界线———————————————————————— -->
<script>
//import XXX from './components/XXX'

export default {
  name: 'my-slide',
  data() {
    return {
      msg: 'this is from my-slide.vue',
      isOpen:true
    }
  },
  methods: {

  }
}
</script>
