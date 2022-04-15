<template>
    <nav class="main-menu">
        <ul class="main-menu__list">
          <router-link to="/">
            <img
              src="./DK-logo.png"
              alt=""
              class="main-menu__list-logo"
            />
          </router-link>
          <router-link to="/projecten">Projecten</router-link>
          <router-link to="/expertise">Expertise</router-link>
          <router-link to="/over">Over mij</router-link>
            <li>
                <a href="#"
                    ><img
                        src="./DK-logo.png"
                        alt=""
                        class="main-menu__list-logo"
                /></a>
            </li>
            <li><a href="#">projecten</a></li>
            <li><a href="#">expertise</a></li>
            <li><a href="#">over mij</a></li>
            <li>
                <DKButton>Contact</DKButton>
            </li>
            <!--            <li>-->
            <!--                <a-->
            <!--                    class=" main-menu__list-icon main-menu__list-icon-bars"-->
            <!--                    href=""-->
            <!--                    v-on:click="MenuOpen"-->
            <!--                >-->
            <!--                    <i class="fa fa-bars"></i>-->
            <!--                </a>-->
            <!--            </li>-->
            <!--            <li>-->
            <!--                <a-->
            <!--                    class="main-menu__list-icon main-menu__list-icon-cross"-->
            <!--                    href=""-->
            <!--                    v-on:click="MenuOpen"-->
            <!--                >-->
            <!--                    <i class="fa fa-times"></i>-->
            <!--                </a>-->
            <!--            </li>-->
        </ul>
    </nav>
</template>

<script>

import DKButton from "./DKButton.vue";

export default {
    components: { DKButton },
    props: {},
    data() {
        return {};
    }
};
</script>

<style>
.main-menu {
    padding: var(--grid-gap-mobile);
    color: var(--color-grey-light);
}

@media (min-width: 320px) {
  .main-menu {
    padding: var(--grid-gap-tablet);
  }
}

@media (min-width: 992px) {
  .main-menu {
    padding: var(--grid-gap-desktop);
  }
}

.main-menu a {
  display: block;
}

.main-menu a:hover {
    color: var(--color-darkest);
}

.main-menu a:active {
    color: var(--color-primary);
}

.main-menu__list {
  display: flex;
  flex-direction: column;
  gap: 2rem;
  align-items: center;
  margin: 0;
  list-style: none;
}

.main-menu__list:first-child {
  padding-left: 0px;
}

@media (min-width: 992px) {
  .main-menu__list {
    flex-direction: row;
  }
}

.main-menu__list-logo {
  max-width: 16rem;
}

.main-menu__list-icon {
    display: block;
}

@media (min-width: 992px) {
  .main-menu__list-icon {
    display: none;
  }
}

.main-menu li {
    padding-right: 2rem;
}

.main-menu li:first-child {
    margin-right: auto;
}

.main-menu a,
button {
    color: var(--color-grey-light);
    font-size: 13px;
    line-height: 1.6em;
    text-transform: uppercase;
    letter-spacing: 1px;
    text-decoration: none;
}

/* @media screen and (max-width: 600px) {
    .main-menu {
        background-color: red;
    }

    .main-menu a:not(:first-child) {
        display: none;
    }

.main-menu__list {
    list-style: none;
    display: flex;
    justify-content: flex-end;
    align-items: center;
    margin: 0;
    height: 5.5rem;
    padding: 0;
}

    .main-menu a.main-menu__list-icon {
        display: block;
    }
}


@media screen and (max-width: 600px) {
    .main-menu.responsive {
        position: relative;
    }
    .main-menu.responsive a.icon {
        position: absolute;
        right: 0;
        top: 0;
    }
    .main-menu.responsive a {
        float: none;
        display: block;
        text-align: left;
    }
} */
</style>
