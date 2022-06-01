<script>
  export let selectedPlanet;
  import Tabs from "../shared/Tabs.svelte";
  let tabs = ["overview", "structure", "geology"];
  let selectedTab;

  const lowercasePlanetName = selectedPlanet.name.toLowerCase();

  console.log(selectedPlanet);

  //console.log(selectedPlanet);
  //planet data will come in via props
  //will have a view controller for the tabs overview, structure, and surface
</script>

<Tabs {tabs} bind:selectedTab />

<div class="container">
  <img
    src={`./img/planet-${lowercasePlanetName}.svg`}
    alt=""
    class="planet-image"
  />
</div>

<!-- 
<h1>{selectedPlanet.name}</h1> -->
<style>
  .container {
    margin: 0 24px;
  }
  .planet-image {
    transform: scale(0.38487973);
  }
</style>
