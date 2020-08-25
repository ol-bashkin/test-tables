<template>
    <a :href="`/${page.slug}`" class="n-link">{{ page.name }}</a>
</template>

<script>
export default {
    props: {
        page: {
            type: Object,
            required: true
        },
        active: {
            type: Boolean,
            default: false
        }
    }
};
</script>

<style lang="scss" scoped>
@import "@/assets/scss/vars";
.n-link {
    text-decoration: none;
    font-weight: bold;
    color: $text;
    font-size: 12px;
    text-transform: uppercase;
    letter-spacing: 3px;
    border-bottom: 1px dotted transparent;
    transition: border-color 0.2s ease-in-out;
    &--active {
        color: $primary;
    }
    &:hover {
        border-bottom-color: $text;
    }
}
</style>
