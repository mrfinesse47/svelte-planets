<script>
  export let selectedPlanet;
  import Tabs from "../shared/Tabs.svelte";
  let tabs = ["overview", "structure", "geology"];
  let selectedTab;
  console.log(selectedPlanet);
</script>

<Tabs {tabs} bind:selectedTab />

<div class="container">
  <img
    src={`./img/planet-${selectedPlanet.name.toLowerCase()}.svg`}
    alt={selectedPlanet.name}
    class="planet-image"
  />
</div>

<div class="blurb-container">
  <h2>{selectedPlanet.name}</h2>
  <p>{selectedPlanet.overview.content}</p>
  <div class="source">
    <h3>
      Source: <a href="http://www.wikipedia.org"
        >Wikipedia <img src="./img/icon-source.svg" alt="Wikipedia" /></a
      >
    </h3>
  </div>
</div>

<div class="numeric-info">
  <div class="rotation-time">{selectedPlanet.rotation}</div>
  <div class="revolution-time">{selectedPlanet.revolution}</div>
  <div class="radius">{selectedPlanet.radius}</div>
  <div class="average-temp">{selectedPlanet.temperature}</div>
</div>

<style>
  .container {
    margin: 0 1.5rem;
    height: 19rem;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .planet-image {
    transform: scale(0.38487973);
  }
  .blurb-container h2 {
    text-align: center;
    text-transform: uppercase;
  }
  .blurb-container p {
    text-align: center;
    font-family: "spartan", sans-serif;
    font-style: normal;
    font-weight: 400;
    font-size: 11px;
    line-height: 22px;
    margin-top: 1rem;
  }
  .blurb-container h3 {
    opacity: 0.5;
    text-align: center;
    margin-top: 32px;
    font-weight: 400;
  }
  .blurb-container h3 a {
    text-decoration: none;
    font-weight: 700;
    color: #fff;
  }
  .numeric-info {
    display: flex;
  }
  .numeric-info div {
    border: 1px solid rgba(255, 255, 255, 0.2);
  }
</style>
