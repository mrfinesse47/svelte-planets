<script>
  export let tabs;
  export let selectedTab = tabs[0];
  function select(e) {
    selectedTab = e.target.id;
  }
</script>

<ul>
  {#each tabs as tab}
    <li
      id={tab}
      class={tab === selectedTab && "selected"}
      on:click={(e) => select(e)}
    >
      {tab}
    </li>
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
    padding: 20px 0.2rem 17px;
  }
  li:hover {
    cursor: pointer;
  }
  li.selected {
    border-bottom: 4px solid #419ebb;
  }
</style>
