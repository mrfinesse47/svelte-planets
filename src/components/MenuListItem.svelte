<script>
  export let planet;
</script>

<li>
  <div class="left-container">
    <div
      class="planet-color-circle"
      style={`background-color:${planet.color};`}
    />
    <p>{planet.name}</p>
  </div>
  <img src="./img/icon-chevron.svg" alt="chevron icon" class="chevron" />
</li>

<style>
  .left-container {
    display: flex;
    align-items: center;
  }
  li {
    display: flex;
    align-items: center;
    justify-content: space-between;
    text-transform: uppercase;
    margin: 1.25rem 1.5rem;
    list-style: none;
    padding-bottom: 19px;
    border-bottom: 1px solid rgba(255, 255, 255, 0.1);
  }
  li p {
    padding-top: 4.5px;
    display: block;
    font-family: "League Spartan", sans-serif;
    font-weight: 700;
    font-size: 0.9375rem;
    letter-spacing: 1.36364px;
    line-height: 1.5625rem;
  }
  .planet-color-circle {
    width: 1.25rem;
    height: 1.25rem;
    background-color: gold;
    border-radius: 50%;
    margin-right: 1.5625rem;
  }
</style>
