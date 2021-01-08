<template>
  <div id="test">
  </div>
</template>

<script>
import * as d3 from 'd3';

export default { 
  name: 'Graph',
  data() {
   return {
     
      points : [
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
          ],
        links : [
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
            },
             {
                source: 2,
                target: 3,
                direction: false,
                id: 'pokebro',
                flow: 10
            }
        ]
     }
 },
 mounted() {
    this.generateArc();
  },
 methods: {
   generateArc() {
    const margin = {top: 20, right: 20, bottom: 30, left: 50},
            width = 1000 - margin.left - margin.right,
            height = 1000 - margin.top - margin.bottom;

    const graph = d3.select("#test")
            .append("svg")
                .attr("width", width + margin.left + margin.right)
                .attr("height", height + margin.top + margin.bottom)
                .append("g")
                    .attr("transform",
                        "translate(" + margin.left + "," + margin.top + ")");
   
    const circle = graph.selectAll("g")
            .data( [this.points, this.links  ])
            .enter()
            .append("g");
  alert(JSON.stringify(circle))
          circle.append("circle")
            .attr("cx", function(d) {
            return d[0]..x;})
            .attr("cy", function(d) {
            return d.pp.y;})
            .attr("r", 5)
            .attr("fill", "green")
            .attr("x1", function(d) {
            return this.points[d.ll.source - 1].x;})
            .attr("y1", function(d) {
            return this.points[d.ll.source - 1].y;})
            .attr("x2", function(d) {
            return this.points[d.ll.target - 1].x;}) 
            .attr("y2", function(d) {
            return this.points[d.ll.target - 1].y;})
            .style("stroke-width", function(d){
                return d.ll.flow;
            })

    const line = graph.selectAll("g")
            .data(this.links)
            .enter()
            .append("g");

            line.append("line")
            .attr("x1", function(d) {
            return this.points[d.source - 1].x;})
            .attr("y1", function(d) {
            return this.points[d.source - 1].y;})
            .attr("x2", function(d) {
            return this.points[d.target - 1].x;}) 
            .attr("y2", function(d) {
            return this.points[d.target - 1].y;})
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
   }
 }
};


</script>

<style scoped>

.line-chart {
  margin: 25px;
    fill: none;
    stroke: #76BF8A;
    stroke-width: 3px;}

.line {
            fill: none;
           
            stroke-width: 5px;
            
            
        }

        .circle {
            fill: blue; 
            
        }

        body {
            background-color: white;
        }

        h3 {
        animation: color-me-in 5s;
        }

        @keyframes color-me-in {
        /* You could think of as "step 1" */
        0% {
            fill: orange;
        }
  /* You could think of as "step 2" */
        100% {
            fill: black;
        }
        }

        .draw {
            fill: none;
            stroke: #7d2d68;
            stroke-width: 17px;

/* Stroke-dasharray property */
            stroke-dasharray: 1000px;
            stroke-dashoffset: 1000px;
            animation: move 2s linear infinite;   
/*     animation-fill-mode: forwards; */
        }

        .draw3 {
            fill: none;
            stroke: #7d2d68;
            stroke-width: 5px;

/* Stroke-dasharray property */
            stroke-dasharray: 10px;
            stroke-dashoffset: 100px;
            animation: move 2s linear infinite;   
/*     animation-fill-mode: forwards; */
        }

        .draw4 {
            fill: none;
            stroke: #7d2d68;
            stroke-width: 5px;

/* Stroke-dasharray property */
            stroke-dasharray: 10px;
            stroke-dashoffset: 0;
            animation: move2 2s linear infinite;   
            outline-offset: 10px;
/*     animation-fill-mode: forwards; */
        }

        .drawNone {
            display:none;
        }

        @keyframes move {
        /* You could think of as "step 1" */
        100% {
        stroke-dashoffset: 0;
        animation-direction: alternate;
            }
        }

        @keyframes move2 {
        /* You could think of as "step 1" */
        100% {
        stroke-dashoffset: 100px;
        animation-direction: alternate;
            }
        }

</style>
