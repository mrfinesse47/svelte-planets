<script>
  import { slide } from "svelte/transition";
  import MenuListItem from "./MenuListItem.svelte";
  export let planets;
  export let isMenuOpen = false;
</script>

{#if isMenuOpen}
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
    list-style: none;
    background-color: #070724;
  }

  @media screen and (min-width: 768px) {
    div {
      position: static;
      width: 100%;
      height: auto;
      top: auto;
      margin: 0;
      padding: 0 3.25rem;
    }
    ul {
      padding: 0;
      display: flex;
      justify-content: space-between;
    }
  }
  @media screen and (min-width: 1440px) {
    div {
      padding: 0 2.5rem;
      width: 41.5625rem;
    }
  }
</style>
