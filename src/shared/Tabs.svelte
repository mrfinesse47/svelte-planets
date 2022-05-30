<script>
  export let tabs = ["overview", "structure", "geology"];
</script>

<h3>tabs</h3>
{#each tabs as tab}
  <p>{tab}</p>
{/each}

<style></style>
