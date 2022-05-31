<script>
  export let tabs = ["overview", "structure", "geology"];
  //hard coded for now
</script>

<ul>
  {#each tabs as tab}
    <li>{tab}</li>
  {/each}
</ul>

<style>
  ul {
    padding: 20px 24px 17px;
    list-style: none;
    display: flex;
    justify-content: space-between;
    border-bottom: 1px solid rgba(255, 255, 255, 0.2);
  }
  li {
    font-weight: 700;
    font-size: 0.5625rem;
    line-height: 0.625rem;
    text-align: center;
    letter-spacing: 0.1205rem;
    text-transform: uppercase;
    padding: 0 0.2rem;
  }
  li .selected {
    color: #ffffff;
  }
</style>
