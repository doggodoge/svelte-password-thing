<script>
  export let character;
  export let index;
</script>

<div class="container {index % 2 == 0 ? 'even-cell' : 'odd-cell'}">
  <p class="character">{character}</p>
  <p class="number">{index}</p>
</div>

<style>
  .container {
    display: flex;
    flex-direction: column;
    padding: 2rem;
    min-width: 5rem;
  }

  .character {
    font-size: 5em;
  }

  .number {
    font-size: small;
  }

  .even-cell {
    background-color: #ffffff;
  }

  .odd-cell {
    background-color: #f0f0f0;
  }
</style>
