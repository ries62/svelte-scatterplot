<script>
// @ts-nocheck

  import data from "./components/data/data.js";
  import AxisX from "./AxisX.svelte";
  import AxisY from "./AxisY.svelte";
  import { scaleLinear } from "d3-scale";

  const width = 1100;
  const height = 700;
  const margin = {
    top: 100,
    right: 100,
    bottom: 100,
    left: 100,
  };
  const innerWidth = width - margin.left - margin.right;
  const innerHeight = height - margin.top - margin.bottom;

  const xScale = scaleLinear().domain([0, 100]).range([0, innerWidth]);
  const yScale = scaleLinear().domain([0, 60]).range([innerHeight, 0]);

  const x = (d) => d.grade;
  const y = (d) => d.hours;
</script>

<svg {width} {height}>
  <g transform="translate({margin.left},{margin.top})">
    <AxisX {innerHeight} {innerWidth} {xScale}/>
    <AxisY {innerHeight} {innerWidth} {yScale}/>
    {#each data as d}
      <circle cx={xScale(x(d))} cy={yScale(y(d))} r="10" fill="blue" />
    {/each}
  </g>
</svg>

<style>
  svg {
    border: 1px solid blue;
  }
</style>
