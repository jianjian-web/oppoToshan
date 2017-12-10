<template>
  <div class='container header'>
    <div class='pc'>
      <div class='logoDiv'>
        <a href="#" class='logo'></a>
      </div>
      <div class='right'>
        <i class='search'></i>
        <i class='user'></i>
      </div>
      <div class='content'>
        <a href="item.url" v-for='(item,index) in title' :key='index' v-text='item.label'></a>
      </div>
    </div>
    <div class='phone'>
      <div class='nav' :class="{active:isToggle}" @click='handleNavClick'>
        <i></i><br>
        <i></i><br>
        <i></i>
      </div>
      <span class='logo-phone'></span>
      <span class='user-phone'></span>
    </div>
    <transition enter-active-class="animated bounceInRight" leave-active-class="animated bounceOutLeft">
      <div v-if='isToggle' class='maskNav'>
          <a href="item.url" v-for='(item,index) in title' :key='index' v-text='item.label'></a>
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  name: 'header',
  data () {
    return {
      isToggle: false
    }
  },
  props: {
    title: {
      type: Array,
      default: []
    }
  },
  methods: {
    handleNavClick () {
      this.isToggle = !this.isToggle
    }
  }
}
</script>

<style scoped lang='less'>
.header{
  position: absolute;
  left: 0;
  top:0;
  right:0;
  height: 60px;
  z-index:100;
  .phone{
    display: none;
  }
  .maskNav{
    display: none;
  }
  line-height: 60px;
  .logoDiv{
    height:100%;
    line-height: 60px;
    float: left;
    .logo{
      display: inline-block;
      vertical-align: middle;
      width:184px;
      height:19px;
      background: url('../assets/img/icon-sprite.png') no-repeat -92px -299px;
      background-size: 454px 420px;
    }
  }
  .right{
    float: right;
    width:170px;
    height:100%;
    line-height: 60px;
    i{
      display: inline-block;
      width:22px;
      height: 22px;
      background: url('../assets/img/icon-sprite.png') no-repeat;
      vertical-align: middle;
      margin-left: 51px;
    }
    .search{
       background-position: -404px -184px;
    }
    .user{
      background-position:-404px -280px;
    }
  }
  .content{
    margin:0 250px;
    height:100%;
    display: flex;
    justify-content: space-around;
    a{
      padding:0 40px;
      color:#000;
    }
  }
  @media screen and (min-width:768px) and (max-width:991px){
  .content{
    a{
        padding:0 5px;
      }
    }
  }
  @media screen and (max-width:767px){
    .pc{
      display: none;
    }
    &{
      height:44px;
    }
    .maskNav{
          display: flex;
          position: fixed;
          padding-top:44px;
          flex-direction: column;
          align-items: center;
          top:0;
          left: 0!important;
          right: 0;
          bottom:0;
          transition: all 0.35s ease-in;
          background:#fff;
          a{
            padding:10px 50px;
            color:#000;
          }
        }
    .phone{
      position: absolute;
      left: 20px;
      right: 20px;
      top:0;
      display: block;
      height:100%;
      z-index: 10;
      text-align: center;
      &:before{
        content: '';
        display: table;
      }
      .active{
        i{
          transform-origin:right center;
        }
        i:nth-child(1){
          transform: rotate3d(0,0,1,-45deg)
        }
        i:nth-child(3){
          opacity: 0;
        }
        i:nth-child(5){
          transform: rotate3d(0,0,1,45deg)
        }
      }
      .nav{
        line-height: 0;
        cursor: pointer;
        float: left;
        margin-top:22px;
        transform:translate(0,-50%);
        i{
          transition: all 0.35s ease-in;
          display: inline-block;
          width:18px;
          border-top:1px solid #000;
          margin-top:5px;
        }
        i:first-child{
          margin-top:0;
        }
      }
      .logo-phone{
        display: inline-block;
        width:184px;
        height:19px;
        background: url('../assets/img/icon-sprite.png') no-repeat -92px -299px;
        transform: scale(0.8);
      }
      .user-phone{
        float: right;
        width:22px;
        height: 22px;
        background: url('../assets/img/icon-sprite.png') no-repeat -404px -280px;
        transform: scale(0.6);
        margin-top:22px;
        transform: translate(0,-50%);
      }
    }
  }
}
</style>

