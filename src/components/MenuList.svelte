<script>
  import { slide } from "svelte/transition";
  import MenuListItem from "./MenuListItem.svelte";
  export let planets;
  export let isMenuOpen = false;
</script>

{#if isMenuOpen}
  <!-- to get transition to work i needed to conditionally render. 
  CSS classes didn't work -->
  <div transition:slide>
    <ul>
      {#each planets as planet}
        <li>
          <MenuListItem {planet} />
        </li>
      {/each}
    </ul>
  </div>
{/if}

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
</style>
