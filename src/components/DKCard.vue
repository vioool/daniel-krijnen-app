<template>
    <div class="dk-projecten">
        testen maarrrrrrrrrrrrrrrrrrr!!!!!!!!!!!!!!!!!!
      <slot />
        <ul>
            <li class="list" v-for="project in entries">
                <div class="card">
                  <img src="../assets/images/DK-Oostenburg.jpg" alt="">
                  <h2 class="names">{{ project.title }}</h2>
                  <p class="cities">{{ project.title }}</p>
                </div>
            </li>
        </ul>
    </div>
</template>

<script>
import axios from "axios";

export default {
    props: {
        project: {
          type: Object,
          required: false,
          default: null
        }
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
.dk-projecten ul{
  display: flex;
  gap: 2rem;
}

.dk-projecten .list {
  list-style-type: none;

}

.dk-projecten .card {
  /* margin: 50px; */
  border: solid var(--color-grey-light) .0125rem;
  width: 15.5rem;
  height: 15.5rem;
}

img {
  width: 15.5rem;
}

</style>
