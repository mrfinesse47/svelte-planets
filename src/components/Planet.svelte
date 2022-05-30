<script>
  import Tabs from "../shared/Tabs.svelte";
  export let selectedPlanet;
  //console.log(selectedPlanet);
  //planet data will come in via props
  //will have a view controller for the tabs overview, structure, and surface
</script>

<Tabs />

<h1>{selectedPlanet.name}</h1>

<style></style>
