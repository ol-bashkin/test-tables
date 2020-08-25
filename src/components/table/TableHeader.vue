<template>
    <thead class="thead">
        <tr class="thead__row">
            <th class="thead__cell">№</th>
            <th
                v-for="(header, index) in headers"
                :key="index"
                v-html="header"
                class="thead__cell"
                :class="{ 'thead__cell--current': current === index + 1 }"
            ></th>
        </tr>
    </thead>
</template>

<script>
export default {
    props: {
        headers: {
            type: Array,
            required: true
        },
        current: {
            type: Number,
            required: true
        }
    }
};
</script>

<style lang="scss" scoped>
@import "@/assets/scss/vars";
.thead {
    &__cell {
        position: sticky;
        top: 0;
        z-index: 2;
        padding: 10px;
        font-weight: bold;
        background-color: #fff;
        border-bottom: 1px solid $text;
        &--current {
            background-color: $primary;
            color: #fff;
        }
    }
}
</style>
