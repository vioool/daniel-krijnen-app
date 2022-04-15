<template>
  <div class="dk-main">
    <slot>
      <h1>Fallback Main</h1>
      <p> Fallback test text van de main component</p>
    </slot>
  </div>
</template>

<script>
export default {
    components: {},
    props: {},
    data() {
        return {};
    }
};
</script>
<style>
.dk-main {
  padding: var(--grid-gap-mobile);
}

@media (min-width: 320px) {
  .dk-main {
    padding: var(--grid-gap-tablet);
  }
}

@media (min-width: 992px) {
  .dk-main {
    padding: var(--grid-gap-desktop);
  }
}
</style>
