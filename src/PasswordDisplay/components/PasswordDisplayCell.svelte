<script>
  import { fly } from 'svelte/transition';

  export let character;
  export let index;

  function isSpecialPasswordCharacter(char) {
    const specialPasswordCharacters = ` !"#$%&'()*+,-./:;<=>?@[\\]^_\`{|}~`;
    return [...specialPasswordCharacters].includes(char);
  }

  function isNumber(char) {
    return !isNaN(char);
  }

  function handleSpecial() {
    return isSpecialPasswordCharacter(character) ? 'special-character' : '';
  }

  function handleNumber() {
    return isNumber(character) ? 'number-character' : '';
  }
</script>

<div
  transition:fly={{ y: 50, duration: 100 }}
  class="container {index % 2 === 0 ? 'even-cell' : 'odd-cell'}"
>
  <p class="character {handleSpecial()} {handleNumber()}">
    {character}
  </p>
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

  .number-character {
    color: cornflowerblue;
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
