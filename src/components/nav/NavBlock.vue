<template>
    <nav class="nav">
        <ul class="nav__list">
            <li v-for="page in pages" :key="page.slug" class="nav__item">
                <NavLink :page="page" />
            </li>
        </ul>
    </nav>
</template>

<script>
import NavLink from "./NavLink.vue";
export default {
    components: {
        NavLink
    },
    props: {
        pages: {
            type: Array,
            required: true
        }
    }
};
</script>

<style lang="scss" scoped>
@import "@/assets/scss/vars";
.nav {
    flex: 0 0 auto;
    display: flex;
    align-items: center;
    justify-content: center;
    height: 60px;
    background-color: $gray;
    &__list {
        display: flex;
        margin: 0;
        list-style: none;
    }
    &__item {
        &:not(:last-child) {
            margin: 0 16px 0 0;
        }
    }
}
</style>
