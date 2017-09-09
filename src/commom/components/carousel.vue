<!-- —————————————↓SCSS———————分界线————————————————————————— -->
<style lang="scss">
.carousel {
  width: 100%;
  height: 100%;
  overflow: hidden;
  position: relative;
  .items-container {
    height: 100%;
    .item-img {
      float: left;
      width: 100%;
      height: 100%;

      background-position: top center;
      background-repeat: no-repeat;

      position: relative;
    }
  }

  .prev,
  .next {


    cursor: pointer;
    position: absolute;
    z-index: 999;
    top: 50%;

    width: 44px;
    margin-top: -40px;

    text-align: center;
    font-size: 60px;
    font-weight: 100;
    line-height: 80px;

    &:hover {
      color: #ccc;
      background: rgba(0, 0, 0, .3);
    }
  }
  .prev {
    left: 2em;
  }
  .next {
    right: 2em;
  }
  .dots {
    position: absolute;
    bottom: 40px;
    left: 50%;
    z-index: 999;
    .dot {
      $width: 12px;

      cursor: pointer;
      box-sizing: border-box;
      border: 2px solid transparent;
      border-radius: 50%;

      width: $width;
      height: $width;
      background: #333;
      margin: $width/2;
      float: left;
      &.active-dot {
        border: 2px solid #f84e4e;
      }
    }
  }
}
</style>

<!-- —————————————↓HTML————————分界线———————————————————————— -->
<template lang="pug">
.carousel(@mouseover="hoverFn",@mouseout="hoverFn")
  template(v-if="hasPrevNext")
    .prev(@click="switchFn",onselectstart="return false") &lt;
    .next(@click="switchFn",onselectstart="return false") &gt;
  ul.dots(:style="{marginLeft:-(len-2)*12 +'px'}")
    li.dot(v-for="n in (len-2)",:class="{'active-dot': activeIndex===n||(activeIndex===(len-1)&&n===1)||(activeIndex===0&&n===4)}",@click="activeIndex=n")

  .items-container(ref="container",:style="{width:imgsArrC.length*100+'%',transform:`translate(-${activeIndex*100/imgsArrC.length}%)`,transition:`transform ${transitionInterval/1000}s`}")
    a.item-img(
      v-for="(v,i) in imgsArrC",
      :style="{width:100/imgsArrC.length+'%',backgroundImage: `url(${v.src})`}"
    )
      p.picTitle(v-if="v.picTitle") {{v.picTitle}}
</template>

<!-- ——————————————↓JS—————————分界线———————————————————————— -->
<script>
//import XXX from './components/XXX'

export default {
  name: 'carousel',
  props: {
    imgsArr: {
      type: Array,
      required: true
    },
    hasPrevNext: {
      type: Boolean,
      default: true
    },
    interval: {
      type: Number,
      default: 5000
    }
  },
  data() {
    return {
      msg: 'this is from carousel.vue',
      activeIndex: 1, // 当前显示第一张
      timer: null,
      isTransitioning: false,
      transitionInterval: 500 // 过渡动画时长

    }
  },
  computed: {
    imgsArrC() { // 在传进来的数据中 增加首位辅助元素
      var first = this.imgsArr[0];
      var last = this.imgsArr[this.imgsArr.length - 1];
      return [last].concat(this.imgsArr, [first])
    },
    len() {
      return this.imgsArrC.length
    },
  },
  methods: {
    switchFn(e) {

      if (this.isTransitioning) return // 动画过渡中不可以进行切换
      e.target.className.indexOf('next') != -1 ? this.activeIndex++ : this.activeIndex--

    },
    startInterval() { // 启动自动轮播函数

      this.timer = setInterval(() => {
        this.activeIndex++
      }, this.interval)

    },
    hoverFn(e) { // 鼠标移入暂停轮播，移出恢复轮播
      if (e.type === 'mouseover') {
        if (this.timer) clearInterval(this.timer)
      } else {
        this.startInterval()
      }
    }
  },
  mounted() {
    this.startInterval()
  },
  watch: {
    activeIndex(newV, oldV) {
      // 在切换到首位辅助元素时， 是由settimeot 自动进行归位，
      // 此时无需进行任何操作(是瞬间完成的，没有过度动画)
      if ((newV === 1 && oldV === (this.len - 1)) || (newV === this.len - 2 && oldV === 0)) return

      this.$refs.container.style.transition = 'transform ' + this.transitionInterval / 1000 + 's'

      this.isTransitioning = true // 为true时表示正在进行transition过渡中，不可以进行切换轮播

      setTimeout(() => {
        if (this.activeIndex === (this.len - 1) || this.activeIndex === 0) {
          // 切换到首尾辅助元素，需要瞬间归位到真实位置，取消transition过渡
          this.$refs.container.style.transition = ''
          this.activeIndex = this.activeIndex === 0 ? this.len - 2 : 1

        }

        this.isTransitioning = false // 为false时表示transition过渡结束，可以进行切换轮播

      }, 500)
    }
  }
}
</script>
