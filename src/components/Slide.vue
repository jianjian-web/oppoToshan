<template>
  <div class='my-slide'>
    <swiper :options="swiperOption" ref="mySwiper">
      <!-- slides -->
      <swiper-slide v-for='(item,index) in slides' :key='index'>
        <a :href="item.url" class='bgimg' :style='{background:"url("+ item.bg +")"}'></a>
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
  export default{
    name: 'slide',
    data () {
      return {
        swiperOption: {
          loop: true,
          autoplay: true,
          pagination: {
            el: '.swiper-pagination'
          },
          on: {
            slideChange: this.handleChange
          }
        }
      }
    },
    props: {
      slides: {
        type: Array,
        default: []
      }
    },
    computed: {
      swiper () {
        return this.$refs.mySwiper.swiper
      }
    },
    methods: {
      handleChange (e) {
        console.dir(this.swiper)
        // TODO 当图片是黑色的那张时，切换后面背景为白色
        // console.dir(this.swiper && this.swiper.activeIndex)
        // console.dir(this.$refs.mySwiper.swiper)
      }
    }
  }
</script>

<style lang='less' scoped>
.my-slide{
  .bgimg{
    display: inline-block;
    height:684px;
    width:100%;
    background-position: center!important;
    background-size:cover!important;
  }
  .swiper-pagination{
    width:100%;
    height:50px;
    line-height: 50px;
  }
  @media screen and (min-width:768px) and (max-width:991px){
    
  }
  @media screen and (max-width:767px){
    .bgimg{
      height:230px;
    }
  }
}
</style>

