<template>
    <div class="dk-projecten">
        testen maarrrrrrrrrrrrrrrrrrr!!!!!!!!!!!!!!!!!!
      <slot />
        <ul>
            <li class="list" v-for="project in entries">
                <div class="card">
                    <h2 class="names">{{ project }}</h2>
                    <p class="cities">{{ project.title }}</p>
                </div>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    props: {
        project: {
          type: Object,
          required: false,
          default: null
        }
    },
    data() {
        return {};
    }
};
</script>

<style>
.dk-projecten .list {
    list-style-type: none;
}

.dk-projecten .card {
    /* margin: 50px; */
    border-radius: 10px;
    border-style: solid;
    border-width: 2px;
    color: white;
    box-shadow: 0 5px 15px 0px rgba(0, 0, 0, 0.6);
}
</style>
