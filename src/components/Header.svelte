<script>
  import MenuList from "./MenuList.svelte";
  import MediaQuery from "../shared/MediaQuery.svelte";
  export let planets;
  export let isMenuOpen; //bound one level up at app

  function toggleMenu() {
    isMenuOpen = !isMenuOpen;
  }
</script>

<header>
  <div class="container">
    <h1>THE PLANETS</h1>
    <MediaQuery query="(max-width: 767px)">
      <MenuList {planets} {isMenuOpen} on:planetSelect />
      <img src="./img/icon-hamburger.svg" alt="menu" on:click={toggleMenu} />
    </MediaQuery>
    <MediaQuery query="(min-width: 768px)">
      <MenuList {planets} isMenuOpen={true} on:planetSelect />
    </MediaQuery>
  </div>
</header>

<style>
  header {
    position: relative;
  }
  .container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 16px 0px 17px;
    border-bottom: 1px solid rgba(255, 255, 255, 0.2);
  }
  img {
    width: 1.5rem;
    height: 1.0625rem;
    margin-right: 1.5rem;
  }
  img:hover {
    cursor: pointer;
  }
  h1 {
    color: #fff;
    font-weight: 400;
    font-size: 1.75rem;
    line-height: 2.25rem;
    letter-spacing: -0.0656rem;
    text-transform: uppercase;
    margin-left: 1.25rem;
  }
</style>
