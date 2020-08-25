<template>
    <tr class="row" :class="{ 'row--even': index % 2 === 0 }">
        <th class="row__header">{{ index + 1 }}</th>
        <td
            v-for="(cell, cellIndex) in row"
            :key="cellIndex"
            :class="{ 'row__cell--current': current === cellIndex + 1 }"
            class="row__cell"
        >
            <component :is="whichComponentToShow" v-bind="{ ...cell.options }" />
        </td>
    </tr>
</template>

<script>
export default {
    props: {
        index: {
            type: Number,
            default: 0
        },
        row: {
            type: Array,
            required: true
        },
        component: {
            type: String,
            required: true
        },
        current: {
            type: Number,
            required: true
        }
    },
    computed: {
        whichComponentToShow() {
            return () => import(`@/components/_base/Base${this.component}.vue`);
        }
    }
};
</script>

<style lang="scss" scoped>
@import "@/assets/scss/vars";
.row {
    &--even {
        background-color: $gray;
    }
    &__header {
        position: sticky;
        left: 0;
        padding: 10px;
        background-color: #fff;
    }
    &__cell {
        font-size: 0;
        padding: 10px;
        .icon {
            fill: $text;
        }
        &--current {
            background-color: $primary;
            .icon {
                fill: #fff;
            }
        }
    }
}
</style>
