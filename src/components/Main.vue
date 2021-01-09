<template>
  <div class="main">
      <h4>Train station <span class="bold">KPI</span></h4>
      <div class="stat">
        <div class="kpi">
            <h5 class="zero">congestion</h5>
            <h1 class="primary zero">{{ kpi.congestion }}</h1>
        </div>
        <div class="kpi">
            <h5 class="zero">distance</h5>
            <h1 class="primary zero">{{ kpi.distance }}</h1>
        </div>
        <div class="kpi">
            <h5 class="zero">resource cost</h5>
            <h1 class="primary zero">{{ kpi[ 'resource cost' ]}}</h1>
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
         <Graph 
          :key="[points,links]"
          v-bind:fetch_data="[points,links]"
         />
      </div>


   </div>  
</template>

<script>
import Graph from './Graph.vue'
import axios from 'axios'

export default {
  name: 'App',
  components: {
    //HelloWorld,
    Graph
  },
  data() {
    return {
        points : [],
        kpi: {},
        links: {}
    }
  },
  mounted(){
    this.fetch_nodes()
    this.fetch_kpi()
    this.fetch_links()
  },
  methods :{
    fetch_nodes(){
       axios.get('http://127.0.0.1:5000/nodes')
        .then(response  => (
          this.points = response.data))
        .catch(function (error) {   
          console.log(error)
      })
    },
    fetch_kpi(){
       axios.get('http://127.0.0.1:5000/kpis')
        .then(response  => (
          this.kpi = response.data))
        .catch(function (error) {   
          console.log(error)
      })
    },
    fetch_links(){
       axios.get('http://127.0.0.1:5000/links')
        .then(response  => (
          this.links = response.data))
        .catch(function (error) {   
          console.log(error)
      })
  }}
}
</script>
<style scoped>

</style>
