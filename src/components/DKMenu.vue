<template>
    <nav class="main-menu">
        <ul class="main-menu__list">
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
                <button v-on:click="contact">contact</button>
            </li>
            <li>
                <a
                    class="main-menu__list-icon-bars"
                    href=""
                    v-on:click="MenuOpen"
                >
                    <i class="fa fa-bars"></i>
                </a>
            </li>
            <li>
                <a
                    class="main-menu__list-icon-cross"
                    href=""
                    v-on:click="MenuOpen"
                >
                    <i class="fa fa-times"></i>
                </a>
            </li>
        </ul>
    </nav>
</template>

<script>
export default {
    components: {},
    props: {},
    data() {
        return {};
    }
};
</script>

<style>
.main-menu {
    width: 100vw;
    background-color: var(--color-lightest);
}

.main-menu a:hover {
    color: var(--color-darkest);
}

.main-menu a.active {
    color: var(--color-secondary);
}

.main-menu__list {
    display: flex;
    flex-direction: column;
    gap: 2rem;
    align-items: center;
    padding: 1rem;
    margin: 0;
    list-style: none;
}

.main-menu__list-logo {
    max-width: 16rem;
}

.main-menu__list-icon {
    display: none;
}

.main-menu li {
    padding-right: 2rem;
}

.main-menu li:first-child {
    margin-right: auto;
    margin-left: 1.25rem;
}

.main-menu a,
button {
    color: var(--color-primary-light);
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
