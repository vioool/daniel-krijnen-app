<template>
  <div class="dk-layout">
    <DKMenu/>
    <DKMain>
      <h1>Main vervanger</h1>deze text vervangt de content van de main component
    </DKMain>
    <DKFooter>
      de header hierboven komt uit de footer component maar dezxe text is een vervanger
    </DKFooter>
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
