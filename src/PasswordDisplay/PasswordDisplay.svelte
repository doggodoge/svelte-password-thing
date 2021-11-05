<script>
  import PasswordDisplayCell from './components/PasswordDisplayCell.svelte';

  export let password;
</script>

<div class="container">
  {#each [...password] as character, index}
    <PasswordDisplayCell {character} {index} />
  {/each}
</div>

<style>
  .container {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
  }
</style>
