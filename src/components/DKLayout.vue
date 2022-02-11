<template>
  <div class="dk-layout">
    <DKMenu/>
    <DKMain>
    </DKMain>
    <DKFooter/>
  </div>
</template>

<script>
import DKMenu from "./DKMenu";
import DKMain from "./DKMain";
import DKFooter from "./DKFooter";

export default {
  components: {
    DKMenu,
    DKMain,
    DKFooter
  },
  props: {},
  data() {
    return {};
  }
};
</script>
<style>
.dk-layout {
  /*display: grid;*/
  /*grid-template-areas: 'header' 'main' 'footer';*/
  /*grid-template-rows: auto 1fr auto;*/
  /*min-height: 100vh;*/
}
</style>
