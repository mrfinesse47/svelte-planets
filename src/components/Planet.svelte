<script>
  export let selectedPlanet;
  import Tabs from "../shared/Tabs.svelte";
  import NumericInfo from "../components/NumericInfo.svelte";
  import MediaQuery from "../shared/MediaQuery.svelte";
  import Blurb from "./Blurb.svelte";
  import PlanetImage from "./PlanetImage.svelte";
  let tabs = ["overview", "structure", "geology"];
  let selectedTab = tabs[0];
</script>

<MediaQuery query="(max-width: 767px)" let:matches>
  {#if matches}
    <Tabs {tabs} bind:selectedTab planetColor={selectedPlanet.color} />
  {/if}
</MediaQuery>

<main>
  <PlanetImage {selectedPlanet} {selectedTab} />
  <Blurb {selectedPlanet} {selectedTab}>
    <MediaQuery query="(min-width: 768px)" let:matches>
      {#if matches}
        <Tabs {tabs} bind:selectedTab planetColor={selectedPlanet.color} />
      {/if}
    </MediaQuery>
  </Blurb>
  <NumericInfo {selectedPlanet} />
</main>

<style>
  main {
    max-width: 450px;
    margin: 0 auto;
  }
  @media screen and (min-width: 767px) {
    main {
      max-width: 100%;
      margin: 0 2.4375rem;
    }
  }
</style>
