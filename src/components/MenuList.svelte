<script>
  import MenuListItem from "./MenuListItem.svelte";
  export let planets;

  //import { slide } from 'svelte/transition';
  //then on click send and event to change the view of main to show a planet
</script>

<!-- <div transition:slide></div> -->
<div class:hidden={false}>
  <ul>
    {#each planets as planet}
      <li>
        <MenuListItem {planet} />
      </li>
    {/each}
  </ul>
</div>

<style>
  div {
    position: absolute;
    padding: 0;
    margin: 0;
    width: 100%;
    height: 80vh;
    top: 100%;
    /* top 100% is 100% of the parents height */
  }
  .hidden {
    display: none;
  }
</style>
