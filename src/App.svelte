<script>
  import Header from "./components/Header.svelte";
  import Planet from "./components/Planet.svelte";
  import { onMount } from "svelte";

  let planets = [];
  let isLoading = true;
  let selectedPlanet;
  let isMenuOpen = false;

  onMount(async () => {
    const res = await fetch(`./data.json`);
    planets = await res.json();
    selectedPlanet = findPlanet("Mercury");
    isLoading = false;
  });

  function selectPlanet(e) {
    {
      selectedPlanet = findPlanet(e.detail.planetName);
      isMenuOpen = false;
    }
  }

  function findPlanet(planetName) {
    return planets.filter((planet) => planet.name === planetName)[0];
  }

  //parse the data store in object then seed header and initial planet
</script>

{#if !isLoading}
  <Header
    {planets}
    bind:isMenuOpen
    on:planetSelect={(e) => {
      selectPlanet(e);
    }}
  />
  <div style={isMenuOpen && "display:none"}>
    <Planet {selectedPlanet} />
  </div>
{:else}
  <p>loading...</p>
{/if}

<style>
</style>
