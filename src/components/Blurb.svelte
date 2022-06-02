<script>
  export let selectedPlanet;
  export let selectedTab;
  const determineParagraph = (selectedTab) => {
    if (selectedTab === "overview") return selectedPlanet.overview.content;
    if (selectedTab === "structure") return selectedPlanet.structure.content;
    if (selectedTab === "geology") return selectedPlanet.geology.content;
  };
</script>

<div class="blub-outer-container">
  <div class="blurb-container">
    <h2>{selectedPlanet.name}</h2>
    <p>{determineParagraph(selectedTab)}</p>
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
</style>
