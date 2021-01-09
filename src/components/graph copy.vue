<template>
<div>
  <svg
    class="svg-demo"
    viewBox="0 0 240 80"
  >
    <text
      class="svg-demo__text"
      x="20"
      y="35"
    >
      {{ title }}
    </text>
  </svg>
  </div>
</template>

<script>
import * as d3 from 'd3';

export default {
  name: 'LineChart',
  props: {
    data: {
      required: true,
      type: Array,
    },
    width: {
      default: 500,
      type: Number,
    },
    height: {
      height: 270,
      type: Number,
    }
  },
};


        var data = [
            {
                name: '1',
                x: 300,
                y: 300
            }, {
                name: '2',
                x: 800,
                y: 300
            }, {
                name: '3',
                x: 550,
                y: 100
            }, {
                name: '4',
                x: 550,
                y: 500
            },
            {
                name: '5',
                x: 20,
                y: 500
            },
            {
                name: '6',
                x: 150,
                y: 200
            }
            ];

        var links = [
            {
                source: 1,
                target: 2,
                direction: false,
                id: 'kostas',
                flow: 10,
                maxCapacity: 70
            },
            {
                source: 2,
                target: 5,
                direction: false,
                id: 'iordanis',
                flow: 20
            },
            {
                source: 3,
                target: 4,
                direction: false,
                id: 'pokebro',
                flow: 10
            },
            {
                source: 6,
                target: 3,
                direction: false,
                id: 'pokebro',
                flow: 10
            }
        ];


        var margin = {top: 0, right: 0, bottom: 0, left: 0},
            width = 640 - margin.left - margin.right,
            height = 400 - margin.top - margin.bottom;

        
        
        var graph = d3.select("div")
            .append("svg")
                .attr("width", width + margin.left + margin.right)
                .attr("height", height + margin.top + margin.bottom)
                .append("g")
                    .attr("transform",
                        "translate(" + margin.left + "," + margin.top + ")");

         

        var circle = graph.selectAll("g")
            .data(data)
            .enter()
            .append("g");
            
            circle.append("circle")
            .attr("cx", function(d) {
            return d.x;})
            .attr("cy", function(d) {
            return d.y;})
            .attr("r", 5)
            .attr("fill", "green")
           
         var line = graph.selectAll("g")
            .data(links, links => links.source, links => links.target)
            .enter()
            .append("g");
            
            line.append("line")
            .attr("id", function(d){
                return d.id;
            })
            .attr("x1", function(d) {
            return data[d.source - 1].x;})
            .attr("y1", function(d) {
            return data[d.source - 1].y;})
            .attr("x2", function(d) {
            return data[d.target - 1].x;}) 
            .attr("y2", function(d) {
            return data[d.target - 1].y;})
            .attr("class", function(d){
                if (d.direction) {
                    return "draw3";
                } else {
                    return "draw4";
                }
                })
            .style("stroke-width", function(d){
                return d.flow;
            })
        
        
            
    repeat();



    function repeat() {
        graph.selectAll("circle")
            .attr("r", 0)
            .transition()
            .ease(d3.easeBounce)
            .delay(function(d, i){ return i*1000; })
            .duration(1000)
            .attr("r", 20);
        }
    

</script>

<style scoped>

.line-chart {
  margin: 25px;
    fill: none;
    stroke: #76BF8A;
    stroke-width: 3px;}

</style>




<style scope>


</style>

