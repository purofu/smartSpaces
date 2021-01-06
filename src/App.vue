<template>
  <div id="app">
    <div class="mainComponent">
    <Header />
    </div>
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import Header from './components/Header.vue'

export default {
  name: 'App',
  components: {
    //HelloWorld,
    Header
  }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap');

$font-stack: 'Inter', sans-serif;

body{
  background: #DFE3EC;
  margin: 0;
  margin: 0px auto;
}

#app {
  font-family: $font-stack;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  width: 100%;
  height:100vh;
  display:flex;
  align-items: center;
  justify-content: center;
}

.mainComponent{
  background: #FFFFFF;
  box-shadow: 0px 0px 60px rgba(14, 40, 96, 0.1);
  border-radius: 10px;
  margin:0, auto;
  width: 1100px;
  height: 800px;
}

.header{
    width: 100%;
    height:70px;
    top:200px;
    margin: 0, 0;
    display:flex;
    justify-content: space-between;
    align-content:center;
    flex-wrap: wrap;
    z-index: 10;
    border-bottom: 1px solid #E8E8EE;;

}
.logo{
  padding-left:22px;
   display:inline-flex;
}
.user{
  padding-right:22px;
  display:inline-flex;
}
.user h4{
  padding-right:14px;
}
h4{
  font-family: $font-stack;
font-style: normal;
font-weight: 600;
font-size: 14px;
line-height: 17px;
color: #585E6C;
}
</style>
