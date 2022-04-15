<template>
  <div>
    <DKDefault></DKDefault>
    hoi! deze texts staat gewoon op de app
    <!--    TODO: paginas maken en routes - beginnen in DKMenu.vue Tutorial: https://vueschool.io/lessons/adding-routes-and-content-->
    <pre> {{ entries }}</pre>
  </div>
</template>

<script>
import axios from "axios";
import DKDefault from "./components/DKLayouts/DKDefault";

export default {
  components: {
    DKDefault
  },
  data() {
    return {
      entries: []
    };
  },
  mounted() {
    this.fetchData();
    console.log('test tekstje vanuit de APPPP');
  },
  methods: {
    fetchData() {
      axios({
        url: "https://viola-craft.test/graphql",
        method: "post",
        data: {
          query: `
            query getProject {
              entries(section: "projecten") {
                title
                url
              }
            }
          `
        }
      }).then((result) => {
        console.log(result);
        this.entries = result.data.data.entries;
      })
    }
  }
};
</script>

<style>
* {
  box-style:border-box;
}

:root {
  --grid-gap-mobile: .75rem;
  --grid-gap-tablet: 1rem;
  --grid-gap-desktop: 4rem;

  --color-lightest: #fcfcfc;
  --color-grey-light: #999;
  --color-grey: #6e6e6e;
  --color-darkest: #111;
  --color-primary: #e30613;

  --gradient: 0 5px 15px 0px rgba(0, 0, 0, 0.6);

  --font-size: 16px;

  /* No 'min-max' queries for xxs as it's the default */
  /* use as follow: @media screen and (min-width: var(--q-xs-min)) */

  /** Minimum widths for breakpoints */
  --q-xs-min: 320px + 1; /* Modern phones portrait */
  --q-sm-min: 576px + 1; /* Modern phones landscape */
  --q-md-min: 768px + 1; /* Tablet / medium devices */
  --q-lg-min: 992px + 1; /* Desktop */
  --q-xl-min: 1260px + 1; /* High res - large desktop */
  --q-xxl-min: 1700px + 1; /* Mega large desktop */

  --q-xs-max: 320px; /* Modern phones portrait */
  --q-sm-max: 576px; /* Modern phones landscape */
  --q-md-max: 768px; /* Tablet / medium devices */
  --q-lg-max: 992px; /* Desktop */
  --q-xl-max: 1260px; /* High res - large desktop */
  --q-xxl-max: 1700px; /* Mega large desktop */
}

body {
  background-color: var(--color-lightest);
  color: var(--color-grey);
}

</style>
