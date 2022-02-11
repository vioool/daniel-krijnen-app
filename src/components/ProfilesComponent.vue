<template>
    <ul class="profiles-component">
        <li
            class="profiles-component__list"
            v-for="profile in profiles"
            :key="profile.id"
            :uri="profile.uri"
        >
            <div class="profiles-component__card">
                <h2 class="profiles-component__card-names">
                    {{ profile.name }}
                </h2>
                <p class="profiles-component__card-cities">
                    {{ profile.city }}
                </p>
            </div>
        </li>
    </ul>
</template>

<script>
export default {
    props: {
        profiles: {
            type: Array
        }
    },
    data() {
        return {};
    }
};
</script>

<style>
.profiles-component {
    display: grid;
    grid-template-columns: repeat 1fr;
    grid-gap: 2rem;
}
.profiles-component__list {
    list-style-type: none;
}

.profiles-component__card {
    border-radius: 10px;
    border-style: solid;
    border-width: 2px;
    color: white;
    box-shadow: 0 5px 15px 0px rgba(0, 0, 0, 0.6);
}

@media only screen and (min-width: 600px) {
    .profiles-component {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media only screen and (min-width: 1200px) {
    .profiles-component {
        grid-template-columns: repeat(3, 1fr);
    }
}
</style>
