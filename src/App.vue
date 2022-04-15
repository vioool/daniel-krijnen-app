<template>
  <div>
    <DKLayout></DKLayout>
    hoi! deze texts staat gewoon op de app
    <!--    TODO: paginas maken en routes - beginnen in DKMenu.vue Tutorial: https://vueschool.io/lessons/adding-routes-and-content-->
    <DKCards>
      Dit vervangt de Fallback content van de DKCardssss
    </DKCards>
    <pre> {{ entries }}</pre>
  </div>
</template>

<script>
import axios from "axios";
import DKLayout from "./components/DKLayout";
import DKCards from "./components/DKCards";

export default {
  components: {
    DKLayout,
    DKCards
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
  --grid-gap-mobile: 1.25rem;
  --grid-gap-tablet: 2rem;
  --grid-gap-desktop: 9rem;

  --color-lightest: #fcfcfc;
  --color-grey-light: #999;
  --color-grey: #6e6e6e;
  --color-darkest: #111;
  --color-primary: #e30613;

  --gradient: 0 5px 15px 0px rgba(0, 0, 0, 0.6);

  --font-size: 16px;
}
/**
 * Minimum widths for breakpoints
 */
  @screen-xs: 320px; /* Modern phones portrait */
  @screen-sm: 576px; /* Modern phones landscape */
  @screen-md: 768px; /* Tablet / medium devices */
  @screen-lg: 992px; /* Desktop */
  @screen-xl: 1260px; /* High res - large desktop */
  @screen-xxl: 1700px; /* Mega large desktop */


  /**
   * Media Queries
   */
  @screen-xs-min: (@screen-xs + 1);
  @screen-sm-min: (@screen-sm + 1);
  @screen-md-min: (@screen-md + 1);
  @screen-lg-min: (@screen-lg + 1);
  @screen-xl-min: (@screen-xl + 1);
  @screen-xxl-min: (@screen-xxl + 1);

/* No minmax queries for xxs as it's the default */
  @q-xxs:    ~'screen and (max-width: 320px)';

  @q-xs-min: ~'screen and (min-width: 320px + 1)';
  @q-xs-max: ~'screen and (max-width: 320px~)';
  @q-xs:     ~'screen and (min-width:' @screen-xs-min~') and (max-width:'@screen-sm~')';

  @q-sm-min: ~'screen and (min-width:' @screen-sm-min~')';
  @q-sm-max: ~'screen and (max-width:' @screen-sm~')';
  @q-sm:     ~'screen and (min-width:' @screen-sm-min~') and (max-width:'@screen-md~')';

  @q-md-min: ~'screen and (min-width:' @screen-md-min~')';
  @q-md-max: ~'screen and (max-width:' @screen-md~')';
  @q-md:     ~'screen and (min-width:' @screen-md-min~') and (max-width:'@screen-lg~')';

  @q-lg-min: ~'screen and (min-width:' @screen-lg-min~')';
  @q-lg-max: ~'screen and (max-width:' @screen-lg~')';
  @q-lg:     ~'screen and (min-width:' @screen-lg-min~') and (max-width:'@screen-xl~')';

  @q-xl-min: ~'screen and (min-width:' @screen-xl-min~')';
  @q-xl-max: ~'screen and (max-width:' @screen-xl')';
  @q-xl:     ~'screen and (min-width:' @screen-xl-min~') and (max-width:'@screen-xxl~')';

  @q-xxl-min: ~'screen and (min-width:' @screen-xxl-min~')';
  @q-xxl-max: ~'screen and (max-width:' @screen-xxl')';
  @q-xxl: @q-xxl-min;


body {
  /*padding: var(--grid-gap-mobile);*/
  padding: var(--grid-gap-desktop);
  background-color: var(--color-lightest);
  color: var(--color-grey);
}

</style>
