<script>
  export let selectedPlanet;
  export let selectedTab;
  const determineImageSrc = (selectedTab, selectedPlanet) => {
    if (selectedTab === "overview" || selectedTab === "geology") {
      return `./img/planet-${selectedPlanet.name.toLowerCase()}.svg`;
    }
    if (selectedTab === "structure") {
      return `./img/planet-${selectedPlanet.name.toLowerCase()}-internal.svg`;
    }
  };
</script>

<div class="image-container">
  <img
    src={determineImageSrc(selectedTab, selectedPlanet)}
    alt={selectedPlanet.name}
    class="planet-image"
  />

  {#if selectedTab === "geology"}
    <img
      src={`./img/geology-${selectedPlanet.name}.png`}
      alt={selectedPlanet.name}
      class="geology-img"
    />
  {/if}
</div>

<style>
  .image-container {
    margin: 0 1.5rem;
    height: 19rem;
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;
  }

  .planet-image {
    transform: scale(0.38487973);
  }
  .geology-img {
    position: absolute;
    width: 6.4638rem;
    height: 7.875rem;
    left: 50%;
    transform: translateX(-50%);
    top: 50%;
  }
  @media screen and (min-width: 767px) {
    .image-container {
      height: 30.5rem;
    }
    .planet-image {
      transform: scale(0.63448276);
    }
    .geology-img {
      top: 62.5%;
    }
  }
</style>
