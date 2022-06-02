<script>
  export let selectedPlanet;
</script>

<div class="image-container">
  <img
    src={`./img/planet-${selectedPlanet.name.toLowerCase()}.svg`}
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
