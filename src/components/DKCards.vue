<template>
    <div class="dk-cards">
        <slot>Fallback content</slot>
        <ul class="dk-cards__list">
            <li class="dk-cards__list-item" v-for="project in entries">
                <DKCard
                  :to="project.url"
                  :title="project.title"
                />
            </li>
        </ul>
    </div>
</template>

<script>
import axios from "axios";
import DKCard from "./DKCard";

export default {
    components: {
      DKCard
    },
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
    console.log('dk-cardsss component testen');
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
.dk-cards__list {
  padding: 0;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 2rem;
}

.dk-cards__list-item {
  /*flex: 100%;*/
  list-style-type: none;
}

/*@media (min-width: 320px) {*/
/*  .dk-cards__list-item {*/
/*    flex: 50%;*/
/*  }*/
/*}*/

/*@media (min-width: 992px) {*/
/*  .dk-cards__list-item {*/
/*    flex: 33%;  }*/
/*}*/

</style>
