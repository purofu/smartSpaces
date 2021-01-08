<template>
  <div class="main">
      <h4>Train station <span class="bold">KPI</span></h4>
      <div class="stat">
        <div class="kpi">
            <h5 class="zero">Total</h5>
            <h1 class="primary zero">4563</h1>
        </div>
        <div class="kpi">
            <h5 class="zero">Total</h5>
            <h1 class="primary zero">4563</h1>
        </div>
        <div class="kpi">
            <h5 class="zero">Total</h5>
            <h1 class="primary zero">4563</h1>
        </div>
        <div class="kpi2">
            <h5 class="zero">Total</h5>
            <h1 class="red zero">4563</h1>
        </div>
      </div>
      <h4>Train station <span class="bold">flow<span class="primary">MAP</span></span></h4>
      <div class="inputs">
        <div class="kpi3">
          <h5 class="zero">Add more people</h5>
          <form class="example" action="action_page.php">
            <input type="text" placeholder="Write number of people" name="search">
            <button type="submit"><i class="fa fa-search"><img src="../assets/plus.svg"></i></button>
          </form>
        </div>
        <div class="kpi3">
          <h5 class="zero">Reduce people</h5>
          <form class="example-red" action="action_page.php">
            <input type="text" placeholder="Write number of people" name="search">
            <button type="submit"><i class="fa fa-search"><img src="../assets/minus.svg"></i></button>
          </form>
        </div>
        <div class="kpi3">
          <h5 class="zero">Add something else</h5>
          <form class="example" action="action_page.php">
            <input type="text" placeholder="Write number of people" name="search">
            <button type="submit"><i class="fa fa-search"><img src="../assets/plus.svg"></i></button>
          </form>
        </div>
      </div>

      <div class='graph'>
         <Graph />
      </div>
   </div>  
</template>

<script>
import Graph from './Graph.vue'

export default {
  name: 'App',
  components: {
    //HelloWorld,
    Graph
  }
}
</script>
<style scoped>

</style>
