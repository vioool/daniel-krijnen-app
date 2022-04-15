<template>
  <div class="dk-default">
    <DKMenu/>
    <Nuxt />
    <DKMain>
      <h1>Main vervanger</h1>deze text vervangt de content van de main component
      <DKCards>
        Dit vervangt de Fallback content van de DKCardssss
      </DKCards>
    </DKMain>
    <DKFooter>
      de header hierboven komt uit de footer component maar dezxe text is een vervanger
    </DKFooter>
  </div>
</template>

<script>
import DKMenu from "../DKMenu";
import DKMain from "../DKMain";
import DKFooter from "../DKFooter";
import DKCards from "../DKCards";

export default {
  components: {
    DKMenu,
    DKMain,
    DKFooter,
    DKCards
  },
  props: {},
  data() {
    return {};
  }
};
</script>
<style>
.dk-default {
  /*display: grid;*/
  /*grid-template-areas: 'header' 'main' 'footer';*/
  /*grid-template-rows: auto 1fr auto;*/
  /*min-height: 100vh;*/
}
</style>
