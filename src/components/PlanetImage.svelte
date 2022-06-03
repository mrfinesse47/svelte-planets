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
</div>

<style>
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
