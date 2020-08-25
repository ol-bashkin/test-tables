<template>
    <svg class="icon" :width="width" :height="height">
        <use v-bind="{ 'xlink:href': `/img/sprites/${sprite}.svg#${name}` }" />
    </svg>
</template>

<script>
export default {
    props: {
        sprite: {
            type: String,
            default: "system_sprite"
        },
        name: {
            type: String,
            required: true
        },
        width: {
            type: [Number, String],
            default: 24
        },
        height: {
            type: [Number, String],
            default: 24
        }
    }
};
</script>
<style lang="scss" scoped>
.icon {
    &__noize {
        fill: url(#noize);
    }
}
</style>
