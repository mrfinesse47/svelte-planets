<script>
  export let selectedPlanet;
  let selectedTab;
  import Tabs from "../shared/Tabs.svelte";
  let tabs = ["overview", "structure", "geology"];

  //console.log(selectedPlanet);
  //planet data will come in via props
  //will have a view controller for the tabs overview, structure, and surface
</script>

<Tabs {tabs} bind:selectedTab />

<h1>{selectedTab}</h1>

<!-- 
<h1>{selectedPlanet.name}</h1> -->
<style></style>
