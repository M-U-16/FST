<svelte:window on:resize={resize}/>

<div class="chart-container">
    <div
        class="population-chart{chartClass?" chart-active":""}"
        bind:this={chart}
    ></div>
</div>

<style>

    .chart-container {
        width: 100%;
        height: 15rem;
    }

    .population-chart {
        width: 100%;
        height: 100%;
    }

    :global(.chart-active text:not(.text-active)){
        opacity: 0.2;
    }

    :global(.chart-active rect:not(.rect-active)) {
        opacity: 0.2;
    }

    :global(.chart-text) {
        font-size: 12px;
    }
    
    @media (min-height: 1500px) {
        .chart-container {
            height: 30rem;
        }
        
        :global(.chart-text) {
            font-size: 1.4rem;
        }
    }
</style>

<script>
    function resize() {
        redraw()
    }
    let chart
    let chartClass = false
    import * as d3 from "d3"
    import { onMount } from "svelte";
    import data from "$lib/provinces.json"

    export let province

    let population = []
    Object.keys(data)
    .forEach(key=>{
        population.push({
            key: data[key].name,
            id: data[key].key,
            value: data[key].population.value,
            color: data[key].color
        })
    })
    population = population.sort((a,b)=>a.value<b.value?-1:0)
    let xScale = d3.scaleBand().domain(population.map(d=>d.key))
    let yScale = d3.scaleLinear().domain([0,3840662])
    
    const margin = {
        top: 30,
        right: 50,
        left: 0,
        bottom: 20,
    };
    
    function redraw() {
        d3.select(chart).html(null)
        let width = d3.select(chart)
            .node().getBoundingClientRect()
            .width - margin.left - margin.right
        let height = d3.select(chart)
            .node().getBoundingClientRect()
            .height - margin.top - margin.bottom
        
        xScale.range([0, width])
        yScale.range([height, 0])

        const svg = d3.select(chart)
            .append("svg")
            .attr("width", width + margin.left + margin.right)
            .attr("height", height + margin.top + margin.bottom)
            .append("g")
            .attr("transform", `translate(${[margin.left, margin.top]})`)
            
        svg.selectAll("bar")
            .data(population)
            .enter()
            .append("rect")
                .attr("x", d=>xScale(d.key))
                .attr("y", d=>yScale(d.value))
                .attr("width", xScale.bandwidth())
                .attr("stroke", "grey")
                .attr("id", d=>d.id+"-rect")
                .attr("stroke-width", "1")
                .attr("height", d=>height-yScale(d.value))
                .attr("fill", d=>d.color)

        svg.selectAll("label-text")
            .data(population)
            .enter().append("text")
            .attr("id", d=>d.id+"-text")
            .attr("class", "chart-text")
            .attr("transform", d => {
                return `translate(${[xScale(d.key), yScale(d.value)-3]})`
            })
            .text(d=>getChartLabel(d.value.toString()))
    }
    
    function getChartLabel(num) {
        if (num.length == 7) {
            return num[0] + "." +
                num.slice(1,3) + " Mio"
        } else {
            return "0."+num.slice(0,2)+" Mio"
        }
    }

    let activeText, activeRect

    $: {
        if (province != "") {
            if (activeRect && activeText) {
                activeRect.classList.remove("rect-active")
                activeText.classList.remove("text-active")
            }

            /* console.log(province) */
            activeText = chart.querySelector("#"+province+"-text")
            activeText.classList.add("text-active")
            activeRect = chart.querySelector("#"+province+"-rect")
            activeRect.classList.add("rect-active")
            
            chartClass = true
        } else {
            chartClass = false
        }
    }
    
    onMount(() => {
        redraw()
    })
</script>