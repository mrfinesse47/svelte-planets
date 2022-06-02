<script>
  export let selectedPlanet;

  import Tabs from "../shared/Tabs.svelte";
  import NumericInfo from "../components/NumericInfo.svelte";
  import MediaQuery from "../shared/MediaQuery.svelte";
  import Blurb from "./Blurb.svelte";
  let tabs = ["overview", "structure", "geology"];
  let selectedTab;
</script>

<MediaQuery query="(max-width: 767px)" let:matches>
  {#if matches}
    <Tabs {tabs} bind:selectedTab planetColor={selectedPlanet.color} />
  {/if}
</MediaQuery>

<main>
  <div class="image-container">
    <img
      src={`./img/planet-${selectedPlanet.name.toLowerCase()}.svg`}
      alt={selectedPlanet.name}
      class="planet-image"
    />
  </div>

  <Blurb {selectedPlanet} {selectedTab}>
    <MediaQuery query="(min-width: 768px)" let:matches>
      {#if matches}
        <Tabs {tabs} bind:selectedTab planetColor={selectedPlanet.color} />
      {/if}
    </MediaQuery></Blurb
  >
  <NumericInfo {selectedPlanet} />
</main>

<style>
  main {
    max-width: 450px;
    margin: 0 auto;
  }

  .image-container {
    margin: 0 1.5rem;
    height: 19rem;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .planet-image {
    transform: scale(0.38487973);
  }
</style>
