<template>
  <div>
    <DKLayout></DKLayout>
    hoi
    <DKCard v-for="project in entries">
      {{ project.title }}
      {{ project.url }}
    </DKCard>
    <pre> {{ entries }}</pre>
  </div>
</template>

<script>
import axios from "axios";
import DKLayout from "./components/DKLayout";
import DKCard from "./components/DKCard";

export default {
  components: {
    DKLayout,
    DKCard
  },
  data() {
    return {
      entries: []
    };
  },
  mounted() {
    this.fetchData();
    console.log('test tekstje');
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
  --color-lightest: #fcfcfc;
  --color-grey-light: #999;
  --color-grey: #6e6e6e;
  --color-darkest: #111;
  --color-primary: #e30613;

  --gradient: 0 5px 15px 0px rgba(0, 0, 0, 0.6);

  --font-size: 16px;
}

body {
  background-color: var(--color-lightest);
  color: var(--color-grey);
}

</style>
