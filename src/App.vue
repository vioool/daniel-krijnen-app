<template>
  <div>
    <DKLayout></DKLayout>
    hoi
    <DKProjecten v-for="project in entries">
      {{ project.title }}
      {{ project.url }}
    </DKProjecten>
    <pre> {{ entries }}</pre>
  </div>
</template>

<script>
import axios from "axios";
import DKLayout from "./components/DKLayout";
import DKProjecten from "./components/DKProjecten";

export default {
  components: {
    DKLayout,
    DKProjecten
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

