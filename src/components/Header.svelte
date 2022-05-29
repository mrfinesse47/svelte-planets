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
    font-weight: 400;
    font-size: 1.75rem;
    line-height: 2.25rem;
    letter-spacing: -0.0656rem;
    text-transform: uppercase;
    margin-left: 1.25rem;
  }
</style>
