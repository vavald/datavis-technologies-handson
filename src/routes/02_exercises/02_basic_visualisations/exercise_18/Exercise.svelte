<script>
    // Dimensions
    const width = 800;
    const height = 600;
    const margin = { top: 5, right: 5, bottom: 25, left: 5 };
    const innerWidth = width - margin.left - margin.right;
    const innerHeight = height - margin.top - margin.bottom;
  
    // Array
    import {scaleLog} from 'd3-scale';
    import {axisBottom} from 'd3-axis';
    import {select} from 'd3-selection';
    let g;
    let transform="translate({margin.left},{margin.top})";
    const values = [2, 4, 6, 7, 9];
    const scale = scaleLog().domain([2,9]).range([100,500]);
    const axis = axisBottom(scale);

  </script>
  
  <svg viewBox="0 0 {width} {height}">
    <g transform="translate({margin.left},{margin.top})">
      {#each values as value}
        <circle cx=400 cy={scale(value)} r=10/>
      {/each}
    </g>
    
  </svg>
  