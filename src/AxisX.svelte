<script>
  export let innerHeight;
  export let innerWidth;
  export let xScale;

  let data = [0, 25, 50, 75, 100];
</script>

<g transform="translate(0,{innerHeight})">
    <line x1=0 x2={innerWidth} y1=0 y2=0 stroke='gray'></line>
  {#each data as d}
    <line x1={xScale(d)} x2={xScale(d)} y1=0 y2=12 stroke='gray' />
    <text x={xScale(d)} y=12 dy=4 text-anchor="middle" dominant-baseline="hanging">{d}</text> 
  {/each}
</g>
