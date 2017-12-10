<template>
  <div id="app">
    <!-- <img src="./assets/logo.png"> -->
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'app'
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  font-size: 14px;
}
*{
  box-sizing: border-box;
}
body,html{
  height:100%;
  padding:0;
  margin:0;
}
ul,li,p{
  list-style: none;
  padding:0;
  margin: 0;
}
.container{
  width:1200px;
  margin:0 auto;
}
a{
  text-decoration: none;
}
@media screen and (min-width:768px) and (max-width:991px){
  .container{
    width:100%;
    padding:0 20px;
  }
}
@media screen and (max-width:767px){
  #app {
  font-size: 12px;
  }
  .container{
    width:100%;
  }
}
</style>
