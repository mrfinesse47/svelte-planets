<script>
  export let selectedPlanet;
</script>

<div class="numeric-info">
  <div>
    <div class="inner-container">
      <div class="title">Rotation Time</div>
      <div class="value">
        {selectedPlanet.rotation}
      </div>
    </div>
  </div>
  <div>
    <div class="inner-container">
      <div class="title">Revolution Time</div>
      <div class="value">
        {selectedPlanet.revolution}
      </div>
    </div>
  </div>
  <div>
    <div class="inner-container">
      <div class="title">Radius</div>
      <div class="value">
        {selectedPlanet.radius}
      </div>
    </div>
  </div>
  <div>
    <div class="inner-container">
      <div class="title">Average Temp.</div>
      <div class="value">
        {selectedPlanet.temperature}
      </div>
    </div>
  </div>
</div>

<style>
  .numeric-info {
    max-width: 69.375rem;
    margin-top: 1.75rem;
    display: flex;
    flex-direction: column;
    text-transform: uppercase;
    padding-bottom: 2.9375rem;
  }
  .numeric-info > div {
    border: 1px solid rgba(255, 255, 255, 0.2);
    width: 100%;
    margin-bottom: 0.5rem;
  }
  .numeric-info .inner-container {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 0.5625rem 1.5rem 0.8125rem;
  }
  .numeric-info .value {
    font-family: "Antonio";
    font-weight: 400;
    font-size: 1.25rem;
    line-height: 1.625rem;
    letter-spacing: -0.0469rem;
  }

  .numeric-info .title {
    font-weight: 700;
    font-size: 0.5rem;
    line-height: 1rem;
    letter-spacing: 0.0455rem;
    opacity: 0.5;
    padding-top: 0.5rem;
  }
  @media screen and (min-width: 768px) {
    .numeric-info {
      flex-direction: row;
      justify-content: space-between;
      margin: 0 auto;
      margin-top: 1.6875rem;
      padding-bottom: 2.25rem;
    }
    .numeric-info > div {
      width: 10.25rem;
      padding: 0;
    }
    .numeric-info .inner-container {
      flex-direction: column;
      align-items: flex-start;
      text-align: left;

      padding: 1rem 3.25rem 1.1875rem 0.9375rem;
    }
    .numeric-info .value {
      margin-top: 0.375rem;
      font-size: 1.5rem;
    }
  }
</style>
