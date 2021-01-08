<template>
  <div id="app">
    <div class="mainComponent">
      <Header />
      <div class="content">
        <Menu />
        <Main />
        <Sidebar />
      </div>
    </div>
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import Header from './components/Header.vue'
import Menu from './components/Menu.vue'
import Main from './components/Main.vue'
import Sidebar from './components/Sidebar.vue'

export default {
  name: 'App',
  components: {
    Header,
    Menu,
    Main,
    Sidebar
  }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap');

$font-stack: 'Inter', sans-serif;
$border-color: #E8E8EE;
$border-light-color: #F4F4FA;
$primary: #0066FF;
$red: #FF808B;
$green: #96D6C3;
$darkGrey:#585E6C;
$lightGrey:#C1C8D8;

body{
  background: #DFE3EC;
  margin: 0;
  font-family: $font-stack;
  font-style: normal;
  font-weight: 400;
  font-size: 12px;
  padding:0px;
  margin:0;
}

a:link {
  color: $primary;
  text-decoration: none;
}

/* visited link */
a:visited {
  color: $primary;
  text-decoration: none;
}

/* mouse over link */
a:hover {
  color: #1254B8;
  text-decoration: none;
}

/* selected link */
a:active {
  color: $primary;
  text-decoration: none;
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
    border-bottom: 1px solid $border-color;
}

.content{
  width: 100%;
  height: 730px;
  display: inline-flex;
}

.main{
  width: 730px;
  height: 729
  px;
  display: flex;
  flex-direction: column;
  justify-content: left;
  flex-wrap: wrap;
  text-align: left;
  padding: 25px 35px;
  background: #F5F5FA;
  box-sizing: border-box;
}

.logo{
  padding-left:22px;
   display:inline-flex;
}
.user{
  padding-right:22px;
  display:inline-flex;
  align-items: center;
  justify-content: center;
}
.user h4{
  padding-right:14px;
}

h1{
  font-family: $font-stack;
  font-style: normal;
  font-weight: 700;
  font-size: 30px;
  padding:0px;
  margin:0;

}


h4{
  font-family: $font-stack;
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  color: $darkGrey;
  padding:0px;
  margin:0;
}

h5{
  font-family: $font-stack;
  font-style: normal;
  font-weight: 600;
  font-size: 12px;
  line-height: 22px;
  text-transform: uppercase;
  color: $lightGrey;
  padding:0px;
  margin:0;
}

p{
  font-family: $font-stack;
  font-style: normal;
  font-weight: 400;
  font-size: 12px;
  padding:0px;
  margin:0px;
}

.bold{
  font-weight: 700;
}
.primary{
  color: $primary;
}

.red{
  color: $red;
}

.green{
  color: $green;
}

.dark-grey{
  color:$darkGrey;
  }

.light-grey{
  color:$lightGrey;
  }

.white{
  color: white;
}

.background-primary{
  background-color: $primary;
}

.background-red{
  background-color: $red;
}

.background-green{
  background-color: $green;
}

.background-dark-grey{
  background-color:$darkGrey;
  }

.background-light-grey{
  background-color:$lightGrey;
  }

.background-white{
  background-color: white;
}


.no-border{
  border: 0px;
  border-right: 0px solid white;
}

.zero{
  padding:0;
  margin:0;
}

.menu{
  width: 75px;
  height:730px;
 
  margin: 0 0;
  display:flex;
  justify-content: space-between;
  align-content: space-between;
  flex-wrap: wrap;
  z-index: 10;
  border-right: 1px solid $border-color;
}

.sidebar{
  width: 100%;
  height:729px;
  margin: 0 0;
  display:flex;
  box-sizing: border-box;
  flex-direction: column;
  justify-content: left;
  align-content: left;
  flex-wrap: wrap;
  z-index: 10;
  padding: 25px 20px;
  border-left: 1px solid $border-color;
}

.holder{
  width: 100%;
  margin: 0 0;
  display:flex;
  box-sizing: border-box;
  flex-direction: column;
  text-align: left;
  justify-content: start;
  align-content: left;
  flex-wrap: wrap;
  z-index: 10;
  padding: 0;
}


.stat{
  width:100%;
  height:85px;
  display:inline-flex;
  align-content: center;
  flex-wrap: wrap;
  background: white;
  padding: 0px;
  border-radius: 10px;
  margin-top: 20px;
  margin-bottom: 30px;
}
.graph{
  width: 660px;
  height: 400px;
  background: white;
  padding: 0px;
  margin-top: 20px;
  border-radius: 10px;
  margin-bottom: 10px;
}


.inputs{
  width:100%;
  display:inline-flex;
  justify-content: space-between;
  flex-wrap: wrap;
  margin-top: 15px;
  padding: 0px;
}


.kpi{
  width:25%;
  height:65px;
  display:flex;
  flex-direction: column;
  justify-content: center;
  align-content: center;
  box-sizing: border-box;
  padding: 0px 0px 0px 20px;
  border-right: 1px solid $border-light-color;
}
.kpi2{
  width:25%;
  height:65px;
  display:flex;
  flex-direction: column;
  justify-content: center;
  align-content: center;
  box-sizing: border-box;
  padding: 0px 0px 0px 20px;
}

.kpi3{
  height:65px;
  display:flex;
  flex-direction: column;
  justify-content: left;
  align-content: center;
  box-sizing: border-box;
}

.status{
  height:46px;
  width:100%;
  display:flex;
  flex-direction: column;
  justify-content: left;
  align-content: space-between;
  flex-wrap: wrap;
  padding-bottom: 10px;
  margin-top: 10px;
  border-bottom: 1px solid $border-light-color;
}

.status .text{
  height:46px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-content: center;
  flex-wrap: wrap;
}

.more{
  height:30px;
  width:100%;
  display:flex;
  flex-direction: column;
  justify-content: left;
  align-content: space-between;
  flex-wrap: wrap;
  padding-bottom: 10px;
  margin-top: 10px;
}
.action{
  box-sizing: border-box;
  height:78px;
  display:flex;
  flex-direction: column;
  justify-content: left;
  align-content: space-between;
  flex-wrap: wrap;
  padding: 16px;
  margin-top: 10px;
  border-radius: 10px;
}

.action .text{
  height:48px;
  display: flex;
  flex-direction: row;
  justify-content: left;
  align-content: center;
  flex-wrap: wrap;
  padding-left:16px;
  margin:0px;
  
}

.more .img{
  height:30px;
  display:flex;
  flex-direction: column;
  justify-content: center;
  align-content: center;
  flex-wrap: wrap;
}



.btn-menu-selected{
  width:75px;
  height:75px;
  display:flex;
  align-items: center;
  justify-content: center;
  border: 0;
  border-right: 4px solid $primary;
}

.btn-menu-unselected{
  width:75px;
  height:75px;
  display:flex;
  align-items: center;
  justify-content: center;
  border: 0;
  background: transparent;
}

.btn-img{
  width:46px;
  height:46px;
  display:flex;
  align-items: center;
  justify-content: center;
  border: 0;
  background: transparent;
}

.btn-img-small{
  width:30px;
  height:30px;
  display:flex;
  align-items: center;
  justify-content: center;
  border: 0;
  background: transparent;
}

form.example{
  width: 208px;
}
/* Style the search field */
form.example input[type=text] {
  padding: 11px;
  height:40px;
  font-family: $font-stack;
  font-style: normal;
  font-weight: normal;
  color: #C1C8D8;
  font-size: 12px;
  float: left;
  width: 80%;
  background-color: #ffffff;
  border: 1px solid $primary;
  box-sizing: border-box;
  border-radius: 4px 0px 0px 4px;
}

.border-top{
  border-top: 1px solid $border-color;
  margin-top: 15px;
  padding-top: 8px;
}

/* Style the submit button */
form.example button {
  float: left;
  width: 40px;
  height: 40px;
  padding: 10px;
  background: $primary;
  color: white;
  font-size: 17px;
  border-radius: 0px 4px 4px 0px;
  border: 0;
  border-left: none; /* Prevent double borders */
}

/* Clear floats */
form.example::after {
  content: "";
  clear: both;
  display: table;
}

form.example-red{
  width: 208px;
}
/* Style the search field */
form.example-red input[type=text] {
  padding: 11px;
  height:40px;
  font-family: $font-stack;
  font-style: normal;
  font-weight: normal;
  color: #C1C8D8;
  font-size: 12px;
  float: left;
  width: 80%;
  background-color: #ffffff;
  border: 1px solid $red;
  box-sizing: border-box;
  border-radius: 4px 0px 0px 4px;
}

/* Style the submit button */
form.example-red button {
  float: left;
  width: 40px;
  height: 40px;
  padding: 10px 10px 20px 10px;
  background:$red;
  color: white;
  border-radius: 0px 4px 4px 0px;
  border: 0;
  border-left: none; /* Prevent double borders */
}

/* Clear floats */
form.example-red::after {
  content: "";
  clear: both;
  display: table;
}

</style>
