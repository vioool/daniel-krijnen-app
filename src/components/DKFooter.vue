<template>
  <div class="dk-footer">
    <h1>Footer</h1>
    <slot>
      <p>Fallback test text van de footer component</p>
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
.dk-footer {
  padding: var(--grid-gap-mobile);
}

@media (min-width: 320px) {
  .dk-footer {
    padding: var(--grid-gap-tablet);
  }
}

@media (min-width: 992px) {
  .dk-footer {
    padding: var(--grid-gap-desktop);
  }
}
</style>
