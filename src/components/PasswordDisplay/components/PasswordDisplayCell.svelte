<script>
  import { fly } from 'svelte/transition';

  export let character;
  export let index;

  function isSpecialPasswordCharacter(char) {
    const specialPasswordCharacters = ` !"#£$%&'()*+,-./:;<=>?@[\\]^_\`{|}~`;
    return [...specialPasswordCharacters].includes(char);
  }

  function isNumber(char) {
    return !isNaN(char);
  }

  function getSpecial() {
    return isSpecialPasswordCharacter(character) ? 'special-character' : '';
  }

  function getNumber() {
    return isNumber(character) ? 'number-character' : '';
  }

  function getCellBackgroundColor() {
    return index % 2 === 0 ? 'even-cell' : 'odd-cell';
  }
</script>

<div
  transition:fly={{ y: 50, duration: 100 }}
  class="container {getCellBackgroundColor()}"
>
  <p class="character {getSpecial()} {getNumber()}">
    {character}
  </p>
  <p class="index">{index}</p>
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

  .even-cell {
    background-color: #ffffff;
  }

  .odd-cell {
    background-color: #f0f0f0;
  }

  .character {
    font-size: 5em;
  }

  .index {
    font-size: small;
    color: darkgray;
  }

  .special-character {
    color: red;
  }

  .number-character {
    color: cornflowerblue;
  }
</style>
