<script>
  import PasswordDisplay from './PasswordDisplay/PasswordDisplay.svelte';

  let password = '';
</script>

<main>
  <h1>Cool <span class="cool-text">Pass</span></h1>
  <input bind:value={password} type="text" />
  <PasswordDisplay {password} />
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
