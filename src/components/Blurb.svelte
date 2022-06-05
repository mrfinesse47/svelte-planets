<script>
  export let selectedPlanet;
  export let selectedTab;
</script>

<div class="blub-outer-container">
  <div class="blurb-container">
    <h2>{selectedPlanet.name}</h2>
    <p>{selectedPlanet[selectedTab].content}</p>
    <div class="source">
      <h3>
        Source: <a href="http://www.wikipedia.org"
          >Wikipedia <img src="./img/icon-source.svg" alt="Wikipedia" /></a
        >
      </h3>
    </div>
  </div>
  <slot />
</div>

<style>
  .blurb-container h2 {
    text-align: center;
    text-transform: uppercase;
  }
  .blurb-container p {
    text-align: center;
    font-family: "spartan", sans-serif;
    font-style: normal;
    font-weight: 400;
    font-size: 0.6875rem;
    line-height: 1.375rem;
    margin-top: 1rem;
  }
  .blurb-container h3 {
    opacity: 0.5;
    text-align: center;
    margin-top: 2rem;
    font-weight: 400;
  }
  .blurb-container h3 a {
    text-decoration: none;
    font-weight: 700;
    color: #fff;
  }

  @media screen and (min-width: 768px) {
    .blub-outer-container {
      display: flex;
      justify-content: space-between;
    }
    .blurb-container {
      width: 49%;
    }
  }
</style>
