<template lang="pug">
#app
  my-header
  my-body
  my-footer
  my-slide

</template>

<script>
import myHeader from 'components/header.vue'
import myBody from 'components/body.vue'
import myFooter from 'components/footer.vue'
import mySlide from 'components/my-slide.vue'

export default {
  name: 'app',
  components: {
    myHeader,
    myBody,
    myFooter,
    mySlide
  }
}
</script>

<style lang="scss">
@import 'src/commom/scss/reset.scss';
@import 'src/icon/bg-icon.scss';
// 对body标签的属性设置在这
body {
  a {
    cursor: pointer;
  }
  background: #1a1b1f;
  background-image: url('/static/img/dot2.main.bg.png');
  background-size: cover;
}

#app {}
</style>
