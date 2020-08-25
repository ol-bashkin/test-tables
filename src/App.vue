<template>
    <div id="app">
        <NavBlock :pages="pages" />
        <component :is="whichPageToShow" />
    </div>
</template>

<script>
import NavBlock from "./components/nav/NavBlock.vue";

export default {
    name: "App",
    components: {
        NavBlock
    },
    data() {
        return {
            pages: [
                {
                    slug: "",
                    component: "home",
                    name: "Главная"
                },
                {
                    slug: "days",
                    component: "days",
                    name: "Дни"
                },
                {
                    slug: "hours",
                    component: "hours",
                    name: "Часы"
                }
            ]
        };
    },
    computed: {
        whichPage() {
            let page = window.location.pathname.slice(1).split("/")[0];
            if (window.history && window.history.state) {
                page = window.history.state;
            }
            return page === "" ? "home" : page;
        },
        isPageExist() {
            return this.pages.some(page => page.component === this.whichPage);
        },
        whichPageToShow() {
            if (this.isPageExist) {
                return () => import(`@/views/${this.whichPage}.vue`);
            }
            return () => import("@/views/error.vue");
        }
    }
};
</script>

<style lang="scss">
@import "@/assets/scss/vars";
body {
    margin: 0;
}
#app {
    font-family: $Avenir;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: $text;
    height: 100vh;
    min-height: 400px;
    display: flex;
    flex-direction: column;
}
</style>
