<script>
  import MenuList from "./MenuList.svelte";
  export let planets;
</script>

<header>
  <div class="container">
    <h1>THE PLANETS</h1>
    <MenuList {planets} />
    <img src="./img/icon-hamburger.svg" alt="menu" />
  </div>
</header>

<style>
  header {
    position: relative;
    border: 1px solid red;
  }
  .container {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  img {
    width: 1.5rem;
    height: 1.0625rem;
  }
  img:hover {
    cursor: pointer;
  }
  h1 {
    color: #fff;
    font-size: 1.75rem;
  }
</style>
