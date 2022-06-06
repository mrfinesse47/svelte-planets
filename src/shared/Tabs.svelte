<script>
  import MediaQuery from "../shared/MediaQuery.svelte";
  export let tabs;
  export let selectedTab;
  export let planetColor;
  function select(e) {
    let t = e.target;
    while (t && !t.id) t = t.parentNode;
    //event bubble until parent id found
    selectedTab = t.id;
  }
</script>

<ul>
  {#each tabs as tab, i}
    <MediaQuery query="(max-width: 767px)" let:matches>
      <li
        id={tab}
        style={tab === selectedTab && matches
          ? `border-bottom: 4px solid ${planetColor};`
          : tab === selectedTab &&
            !matches &&
            `background-color:${planetColor};
            `}
        on:click={(e) => select(e)}
      >
        {#if matches}
          {tab}
        {:else}
          <div class="mini-container">
            <div class="number">{`0${i}`}</div>
            <div class="text">{tab}</div>
          </div>
        {/if}
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

  @media screen and (min-width: 768px) {
    ul {
      flex-direction: column;
      padding: 0;
      height: 9.5rem;
      margin: 0;
      margin-top: 56px;
      border-bottom: none;
      justify-content: space-between;
    }
    li:hover {
      background-color: #d8d8d8;
    }
    li {
      width: 281px;
      height: 40px;
      border: 1px solid rgba(255, 255, 255, 0.2);
      line-height: 25px;
      display: flex;
    }
    .mini-container {
      display: flex;
      justify-content: flex-start;
      align-items: center;
    }
    .mini-container .number {
      padding-left: 1.25rem;
      padding-right: 1.0625rem;
      opacity: 0.5;
    }
  }
</style>
