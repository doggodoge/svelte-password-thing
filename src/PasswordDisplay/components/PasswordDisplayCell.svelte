<script>
  export let character;
  export let index;

  function checkIfSpecialPasswordCharacter(char) {
    const specialPasswordCharacters = ` !"#$%&'()*+,-./:;<=>?@[\\]^_\`{|}~`;
    return [...specialPasswordCharacters].find(char);
  }


  const isSpecialPasswordCharacter = checkIfSpecialPasswordCharacter(character);
</script>

<div class="container {index % 2 === 0 ? 'even-cell' : 'odd-cell'}">
  <p class="character {isSpecialPasswordCharacter ? 'special-character' : ''}">{character}</p>
  <p class="number">{index}</p>
</div>

<style>
  .container {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    min-height: 10rem;
    padding: 2rem;
    min-width: 5rem;
  }

  .character {
    font-size: 5em;
  }

  .special-character {
    color: red;
  }

  .number {
    font-size: small;
    color: darkgray;
  }

  .even-cell {
    background-color: #ffffff;
  }

  .odd-cell {
    background-color: #f0f0f0;
  }
</style>
