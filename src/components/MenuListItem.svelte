<script>
  export let planet;
</script>

<li>
  <div class="left-container">
    <div class="planet-color-circle" />
    <p>{planet.name}</p>
  </div>
</li>

<style>
  .left-container {
    display: flex;
  }
  li {
    text-transform: uppercase;
    margin: 1.25rem 1.5rem;
    list-style: none;
    padding-bottom: 19px;
    border-bottom: 1px solid rgba(255, 255, 255, 0.1);
  }
  li p {
    font-family: "League Spartan", sans-serif;
    font-weight: 700;
    font-size: 0.9375rem;
    letter-spacing: 0.0852rem;
    line-height: 1.5625rem;
  }
  .planet-color-circle {
    width: 20px;
    height: 20px;
    background-color: gold;
    border-radius: 50%;
    margin-right: 25px;
  }
</style>
