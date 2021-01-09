<template>
  <div class="mainbar">
      <div class="text">
        <h4>Train station <tagname class="black">KPI</tagname></h4>
      </div>
      <div class="total">
        <div class="box">
            <h5>TOTAL</h5> 
            <h2>594</h2>
        </div>
         <div class="box">
            <h5>TOTAL</h5> 
            <h2>594</h2>
        </div>
         <div class="box">
            <h5>TOTAL</h5> 
            <h2>594</h2>
        </div>
        <div class="box border-zero">
            <h5>TOTAL</h5> 
            <h2>594</h2>
        </div>
      </div>
      <div class="text2"><h4>Train station flow<tagname class="blue">Map</tagname></h4></div>
      
        <div class="scopebox">
          
           <div class="scope"> 
              <label for="add"><h5>ADD MORE PEOPLE</h5></label>
              <form class="inputs">
                <input type="input" name="add" id="add" class="input-blue" placeholder="write number of people"><button type="submit" class="btn-blue"><i class="fa fa-search"><img src="../assets/plus.svg"></i></button>
              </form>
            </div> 

            <div class="scope"> 
              <label for="add"><h5>REDUCE PEOPLE</h5></label>
              <form class="inputs">
                <input type="input" name="add" class="input-red" id="add" placeholder="write number of people"><button type="submit" class="btn-red"><i class="fa fa-search"><img src="../assets/minus.svg"></i></button>
              </form>
            </div>

            <div class="scope"> 
              <label for="add"><h5>ADD SOMETHING ELSE</h5></label>
              <form class="inputs">
                <input type="input" name="add"  class="input-blue" id="add" placeholder="write number of people"><button type="submit" class="btn-blue"><i class="fa fa-search"><img src="../assets/plus.svg"></i></button>
              </form>
            </div>
        </div>
        <div class="graph">
              <lines />
          
          </div>
      </div>
</template>
<script>
import lines from './lines.vue'


export default {
  name: 'App',
  components: {
    //HelloWorld,
    lines
  }
}


</script>

<style scope>


</style>

