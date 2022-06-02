<script>
  export let selectedPlanet;
  import Tabs from "../shared/Tabs.svelte";
  let tabs = ["overview", "structure", "geology"];
  let selectedTab;

  const lowercasePlanetName = selectedPlanet.name.toLowerCase();
</script>

<Tabs {tabs} bind:selectedTab />

<div class="container">
  <img
    src={`./img/planet-${lowercasePlanetName}.svg`}
    alt={selectedPlanet.name}
    class="planet-image"
  />
</div>

<!-- 
<h1>{selectedPlanet.name}</h1> -->
<style>
  .container {
    margin: 0 1.5rem;
    height: 28.75rem;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .planet-image {
    transform: scale(0.38487973);
  }
</style>
