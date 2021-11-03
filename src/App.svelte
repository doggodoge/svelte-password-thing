<script>
  import PasswordDisplay from "./PasswordDisplay/PasswordDisplay.svelte";

  export let name;

  let password = 'Simple Test';
</script>

<main>
  <input bind:value={password} type="text">
  <PasswordDisplay password={password} />
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    margin: 0 auto;
  }

  .cool-text {
    color: red;
  }
</style>
