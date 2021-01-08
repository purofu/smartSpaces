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
            },
            {
                name: '7',
                x: 150,
                y: 11
            }
          ],
        links : [
            {
                source: 1,
                target: 2,
                direction: false,
                id: 'kostas',
                flow: 2,
                maxCapacity: 70
            },
            {
                source: 5,
                target: 2,
                direction: false,
                id: 'iordanis',
                flow: 3
            },
            {
                source: 3,
                target: 4,
                direction: true,
                id: 'pokebro',
                flow: 1
            },
            {
                source: 6,
                target: 3,
                direction: false,
                id: 'pokebro',
                flow: 2
            },
             {
                source: 2,
                target: 3,
                direction: false,
                id: 'pokebro',
                flow: 3
            },
            {
                source: 3,
                target: 7,
                direction: true,
                id: 'pokebro',
                flow: 6
            }
        ]
     }
 },
 mounted() {
    this.generateArc();
  },
 methods: {
   generateArc() {
    const pointer = this.points;

    const margin = {top: 20, right: 20, bottom: 30, left: 50},
            width = 660 - margin.left - margin.right,
            height = 400 - margin.top - margin.bottom;
  

    const xScale = d3.scaleLinear()
            .domain([0, d3.max(pointer, d => d.x)])
            .range([width, 0]);

    const yScale = d3.scaleLinear()
            .domain([0, d3.max(pointer, d => d.y)])
            .range([0, height]);


    
    const graph = d3.select("#test")
            .append("svg")
                .attr("width", width + margin.left + margin.right)
                .attr("height", height + margin.top + margin.bottom)
    
    const lines = d3.select("svg")                
                .append("g")
                    .attr("id", "lines")
                    .attr("transform",
                        "translate(" + margin.left + "," + margin.top + ")");


    const circles = d3.select("svg")
                .append("g")
                    .attr("id", "cirlces")
                    .attr("transform",
                        "translate(" + margin.left + "," + margin.top + ")");
        
    
   
    const circle = circles.selectAll("circles")
            .data(this.points)
            .enter()
            .append("g");
            
            circle.append("circle")
            .attr("cx", function(d) {
            return xScale(d.x);})
            .attr("cy", function(d) {
            return yScale(d.y);})
            .attr("r", 1)
            .attr("class", "circle")
    const line = lines.selectAll("lines")
            .data(this.links)
            .enter()
            .append("g");
            
            line.append("line")
            .attr("id", function(d){
                return d.id;
            })
            .attr("x1", function(d) {
            return xScale(pointer[d.source - 1].x);})
            .attr("y1", function(d) {
            return yScale(pointer[d.source - 1].y);})
            .attr("x2", function(d) {
            return xScale(pointer[d.target - 1].x);}) 
            .attr("y2", function(d) {
            return yScale(pointer[d.target - 1].y);})
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
            //.delay(function(d, i){ return i*1000; })
            .duration(1000)
            .attr("r", 6);
        }
   }
 }
};


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
            fill: $primary; 
            
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
            stroke-dasharray:  600px;
            stroke-dashoffset: 1000px;
            animation: move 2s linear infinite;   
/*     animation-fill-mode: forwards; */
        }

        .draw3 {
            fill: none;
            stroke: $primary;
            stroke-width: 5px;

/* Stroke-dasharray property */
            stroke-dasharray: 10px;
            stroke-dashoffset: 100px;
            animation: move 2s linear infinite;   
/*     animation-fill-mode: forwards; */
        }

        .draw4 {
            fill: none;
            stroke: $red;
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
