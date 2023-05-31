<script>
  export let innerHeight;
  export let innerWidth;
  export let yScale;

  let data = yScale.ticks(4)
</script>

<g transform="translate(0,0)">
    <line x1=0 x2=0 y1=0 y2={innerHeight} stroke='gray'></line>
  {#each data as d}
    <line x1=0 x2=-12 y1={yScale(d)} y2={yScale(d)} stroke='gray' />
    <text x=-12 y={yScale(d)} dx=-6 text-anchor="end" dominant-baseline="middle">{d}</text> 
  {/each}
</g>
