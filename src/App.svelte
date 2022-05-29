<script>
  import Header from "./components/Header.svelte";
  import Planet from "./components/Planet.svelte";
  import { onMount } from "svelte";

  let planets = [];
  let isLoading = true;

  onMount(async () => {
    const res = await fetch(`./data.json`);
    planets = await res.json();
    isLoading = false;
  });

  //parse the data store in object then seed header and initial planet
</script>

{#if !isLoading}
  <Header {planets} />
  <Planet />
{:else}
  <p>loading...</p>
{/if}

<style>
</style>
