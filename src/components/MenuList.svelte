<script>
  import { slide } from "svelte/transition";
  import MenuListItem from "./MenuListItem.svelte";
  export let planets;
  export let isMenuOpen = false;
</script>

{#if isMenuOpen}
  <!-- to get svelge transition to work i needed to conditionally render. 
  CSS classes didn't work -->
  <div transition:slide>
    <ul>
      {#each planets as planet}
        <li>
          <MenuListItem {planet} on:planetSelect />
        </li>
      {/each}
    </ul>
  </div>
{/if}

<style>
  div {
    background-color: #070724;
    position: absolute;
    padding: 0;
    margin: 0;
    width: 100%;
    height: 80vh;
    top: 100%;
    z-index: 5;
    /* top 100% is 100% of the parents height */
  }
  ul {
    padding-top: 1.5rem;
  }
</style>
