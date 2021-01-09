<template>
  <div id="app">
    <div class="mainComponent">
      <Header />
      <div class="main">
        <HelloWorld />
        <graph />
          
        <rightbar />
      </div>
    </div>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Header from './components/Header.vue'
import graph from './components/graph.vue'
import rightbar from './components/rightbar.vue'


export default {
  name: 'App',
  components: {
    HelloWorld,
    Header,
    graph,
    rightbar
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
  text-align: left;
}

.main {
  display:inline-flex;
  justify-content: left;
  width:100%;
  height:730px;
}

.mainbar {
  
  width: 730px;
  background-color: #F5F5FA;
  padding-left:25px;
  padding-right:25px;
}

#app {
  font-family: $font-stack;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
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
h4{
  font-family: Inter;
  font-style: normal;
  font-weight: normal;
  font-size: 14px;
  line-height: 17px;
}
.blue{
  color:blue;
}
.red{
  color:red;
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
    border-bottom: 1px solid #E8E8EE;
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

.sidebar{
    display:flex-wrap;
    justify-content:space-between;
    align-items:space-around;
    border-right:1px solid #E8E8EE;
    width: 75px;
    height: 730px;
    margin: 0 ,auto;
}

.g1{
  padding:10px;  
  border-right: 4px solid #0066FF;
}

.g2{
  padding:10px; 
}

.g3{
  padding:10px;
}

.text h5{
  padding-top:30px;
  padding-bottom:15px;
  text-align:left;
  width: 109px;
  height: 17px;   
}

.text2 h5{
  padding-top:30px;
  padding-bottom:15px;
  text-align:left;
  width: 148px;
  height: 17px;  
  font-size: 14px;
 

}


h2{
  margin:0px;
  padding:0px;
  font-family: Inter;
  font-style: normal;
  font-weight: bold;
  font-size: 30px;

}

h5{
  margin:0px;
  padding:0px;
  font-family: Inter;
  font-style: normal;
  font-weight: 600;
  font-size: 12px;
  color: #C1C8D8;
}
.total h2{
  color:blue;
}

.total{
  width: 700px;
  height: 83px;
  display:flex;
  justify-content: center;
  align-items: center;
  background-color:white;
  background: #FFFFFF;
  border-radius: 10px;
  margin:0 auto;
}

.box  {
  width:25%;
  padding-left:20px;
  height:45px;
  display:flex;
  flex-direction: column;
  justify-content: center;
  align-content: center;
  border-right: 1px solid #E8E8EE;
}

.border-zero{
  border:0px;
}

.btn-blue{
  height:40px;
  width: 40px;
  background: #0066FF;
  border-radius: 0px 4px 4px 0px;
  border:0px;
}
.btn-red{
  height:40px;
  width: 40px;
  background: #FF808B;
  border-radius: 0px 4px 4px 0px;
  border:0px;
}

.input-blue{
    border-radius: 4px 0px 0px 4px;
    border: 1px solid #0066FF;
    width: 208px;

}

.input-red{
    border-radius: 4px 0px 0px 4px;
    border: 1px solid #FF808B;
    width: 208px;

}


label{
  display:flex;
  justify-content:flex-start;
  align-items:flex-start;
  padding-bottom:10px;
  
}

.inputs{
  display:flex;
  width:80%;
}
.scope{
  height: 35px;
  width:210px;
 
}


.scopebox{
  display:flex;
  height:70px;
  width:700px;
  justify-content:space-around;
  
  box-sizing: border-box;
  border-radius: 4px;
  
}

.graph{
  width: 700px;
  height: 400px;
  background-color:#FFFFFF;
  box-shadow: 0px 0px 20px rgba(8, 34, 72, 0.05);
  border-radius: 10px;
  padding-top:20px;
  margin:0 auto;

}
.rightbar{
  width:300px;
  height:730px;
  
}

.text3 h5{
  font-family: Inter;
  font-style: normal;
  font-weight: 500;
  font-size: 12px;
  line-height: 15px;
  padding-left:18px;
  text-align:center;
  width: 210px;
   
}

.text3 h4{
  padding-top:20px;
  padding-left:18px;
  width: 150px;
     
  font-size: 14px;
}
.cautionBox{
  
  width:260px;
  height:240px;
  padding-top:10px;
}
.caBox{
  display:flex;
  justify-content:space-around;
  
  width:260px;
  height:50px;
  padding-left:10px;
  padding-top:10px;
  padding-bottom:10px;
  border-bottom: 1px solid #F4F4FA;
}

.redArrow{
  background:white;
  border-radius: 0px 4px 4px 0px;
  border:0px;

}
.blueArrow{
  background:white;
  border-radius: 0px 4px 4px 0px;
  border:0px;

}
.caBox h4{
  display:flex;
  font-size:10px;
}
.caBox h5{
  font-size: 14px;
}
.textarea{
  display:flex;
  justify-content:center;
  align-items:flex-end;
  flex-direction: column;

}
.text4{ 
  display:flex;
  width:260px;
  justify-content:space-between;
  padding-left:10px;
  padding-top:10px;
  padding-bottom:10px;
  font-size: 12px;
  
  
}
.text4 h5{
  color:#1254B8;
}
.directionBox{
  display:flex-wrap;
  width:260px;
  height:260px;
  padding:12px;
  
  
  
}
.dir{
  display:inline-flex;
  width:260px;
  height:80px;
  background-color:#FF808B;
  border-radius:12px;
  justify-content:space-around;
  align-items:space-around;
  
  
}
.dir , .dirc h5{
  color:white;
}
.dirc{
  display:inline-flex;
  width:260px;
  height:80px;
  background-color:#96D6C3;
  border-radius:12px;
  justify-content:space-around;
  align-items:space-between;
  
}

</style>
