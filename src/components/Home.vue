<template>
  <div class="home">
   <my-header :title='titleArr'></my-header>
   <my-slide :slides='slideItems'></my-slide>
  </div>
</template>

<script>
import myHeader from './Header'
import mySlide from './Slide'
export default {
  name: 'home',
  data () {
    return {
      titleArr: [
        {
          label: '首页',
          url: 'https:www.baidu.com'
        },
        {
          label: '消息',
          url: 'http:www.baidu.com'
        },
        {
          label: '话题',
          url: 'http:www.baidu.com'
        },
        {
          label: '动态',
          url: 'http:www.baidu.com'
        },
        {
          label: '官网',
          url: 'http:www.baidu.com'
        }
      ],
      slideItems: [
        {
          bg: require('../assets/img/slide1.jpg'),
          url: 'http://hd.oppo.com/act/m/jietou/index.html'
        },
        {
          bg: require('../assets/img/slide2.jpg'),
          url: 'https://hd.oppo.com/act/m/2017/xingfuxiaowu/index.html'
        },
        {
          bg: require('../assets/img/slide3.jpg'),
          url: 'https://www.oppo.cn/thread-170161646-1'
        }
      ]
    }
  },
  components: {
    myHeader, mySlide
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
