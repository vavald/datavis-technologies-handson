<script>
    // Dimensions
    const width = 800;
    const height = 100;
    const margin = { top: 5, right: 5, bottom: 5, left: 5 };
    const innerWidth = width - margin.left - margin.right;
    const innerHeight = height - margin.top - margin.bottom;
  
    // Array
    import { scaleLog } from "d3-scale";
    const values = [2, 4, 6, 7, 9];
    const scale = scaleLog(values)
  </script>
  
  <svg viewBox="0 0 {width} {height}">
    <g transform="translate({margin.left},{margin.top})">
      <circle cx=10 cy=10 r=10 transform={scale}/>
    </g>
  </svg>
  