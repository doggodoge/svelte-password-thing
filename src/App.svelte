<script>
  import PasswordDisplay from "./PasswordDisplay/PasswordDisplay.svelte";

  export let name;
</script>

<main>
  <h1>Hello, <span class="cool-text">{name}!</span></h1>
  <PasswordDisplay password="Cool" />
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  .cool-text {
    color: red;
  }
</style>
