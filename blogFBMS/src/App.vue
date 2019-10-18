<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
*{
  margin:0;
  padding:0;
}
li{
  list-style: none;
}
img{
  display: block;
}
a{
  text-decoration: none;
}
input{
  outline: none;
}
/* 字体颜色 */
.fc3{
  color:#333;
}
.fc6{
  color:#666;
}
.fc9{
  color:#999;
}
.fcc{
  color:#ccc;
}
.fcf{
  color:#fff;
}
/* 弹性盒布局 */
.df{
  display: flex;
}
.dfc{
  display: flex;
  flex-direction: column;
}
.jac{
  align-items: center;
  justify-content: center;
}
.alc{
  align-items: center;
}
.jsb{
  justify-content: space-between;
}
.jsa{
  justify-content: space-around;
}
/* 字体大小 */
.f12{
  font-size: 12px;
}
.f14{
  font-size: 14px;
}
.f16{
  font-size: 16px;
}
.f18{
  font-size: 18px;
}
.f20{
  font-size: 20px;
}
.f22{
  font-size: 22px;
}
.f24{
  font-size: 24px;
}
.f26{
  font-size: 26px;
}
.f28{
  font-size: 28px;
}
.f32{
  font-size: 32px;
}
.tc{
  text-align: center;
}
</style>
