<script>
    // Dimensions
    const width = 800;
    const height = 300;
    const margin = { top: 20, right: 5, bottom: 5, left: 5 };
    const innerWidth = width - margin.left - margin.right;
    const innerHeight = height - margin.top - margin.bottom;
  
    // Array
    import {scaleLinear} from 'd3-scale';
    import {scaleOrdinal,schemeDark2} from 'd3-scale-chromatic';
import { scale } from 'svelte/types/runtime/transition';
    const values = [
      { x: 2, y: 1, category: "cat1" },
      { x: 4, y: 2, category: "cat3" },
      { x: 6, y: 1, category: "cat2" },
      { x: 7, y: 3, category: "cat3" },
      { x: 9, y: 1, category: "cat2" }
    ];
    const scaleX=scaleLinear().domain([1,10]).range([0,innerWidth]);
    const scaleY=scaleLinear().domain([0,4]).range([0,innerHeight]);
    const scale_color=scaleOrdinal(schemeDark2); 
  </script>
  
  <svg viewBox="0 0 {width} {height}">
    <g transform="translate({margin.left},{margin.top})">
      <!--  -->
      {#each values as value}
      <circle 
      cx = {scaleX(value.x)} 
      cy = {scaleY(value.y)} 
      r=10 
      style={"fill:" + scale_color(value.category)}
      />
      {/each}
    </g>
  </svg>
  
  <style>
    text {
      text-anchor: middle;
      font-size: small;
    }
  </style>
  