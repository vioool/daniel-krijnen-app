<template>
  <button class="dk-button">
    <slot>
      Click Me!
    </slot>
  </button>
</template>

<script>

</script>

<style>
button {
  display: inline-block;
  border: none;
  padding: 1rem 2rem;
  margin: 0;
  text-decoration: none;
  background: var(--color-grey-light);
  color: var(--color-lightest);
  cursor: pointer;
  text-align: center;
  transition: background 250ms ease-in-out, transform 150ms ease;
  -webkit-appearance: none;
  -moz-appearance: none;
}

button:hover,
button:focus {
  background: var(--color-grey);
}

button:focus {
  outline: solid var(--color-lightest) .0125rem;
  outline-offset: -.25rem;
}

button:active {
  transform: scale(0.99);
}

</style>
