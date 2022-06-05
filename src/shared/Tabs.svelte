<script>
  import MediaQuery from "../shared/MediaQuery.svelte";
  export let tabs;
  export let selectedTab;
  function select(e) {
    selectedTab = e.target.id;
  }

  export let planetColor;
</script>

<ul>
  {#each tabs as tab}
    <MediaQuery query="(max-width: 767px)" let:matches>
      <li
        id={tab}
        style={tab === selectedTab && matches
          ? `border-bottom: 4px solid ${planetColor};`
          : !matches &&
            tab === selectedTab &&
            `background-color:${planetColor}`}
        on:click={(e) => select(e)}
      >
        {tab}
      </li>
    </MediaQuery>
  {/each}
</ul>

<style>
  ul {
    padding: 0px 24px 0px;
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
    padding: 1.25rem 3.2px 1.0625rem;
  }
  li:hover {
    cursor: pointer;
  }
  @media screen and (min-width: 767px) {
    ul {
      flex-direction: column;
      width: 40.783%;
      margin: 0;
      margin-top: 56px;
      border-bottom: none;
      justify-content: center;
    }
  }
</style>
