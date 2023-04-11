<script>
    // Dimensions
    const width = 800;
    const height = 600;
    const margin = { top: 5, right: 5, bottom: 5, left: 5 };
    const innerWidth = width - margin.left - margin.right;
    const innerHeight = height - margin.top - margin.bottom;
  
    // Array
    import {scaleLog} from 'd3-scale';
    const values = [2, 4, 6, 7, 9];
    const scale = scaleLog().domain([2,9]).range([100,500]);
  </script>
  
  <svg viewBox="0 0 800 600" >
    <g transform="translate({margin.left},{margin.top})">
      {#each values as value}
        <circle cx=400 cy={scale(value)} r=10/>
      {/each}
    </g>
  </svg>
  