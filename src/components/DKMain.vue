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
