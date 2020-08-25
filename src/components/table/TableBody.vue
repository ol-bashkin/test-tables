<template>
    <tbody>
        <TableRow
            v-for="(row, index) in tbody"
            :row="row"
            :index="index"
            :component="component"
            :current="current"
            :key="index"
        />
    </tbody>
</template>

<script>
import TableRow from "./TableRow.vue";
export default {
    components: {
        TableRow
    },
    props: {
        tbody: {
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
    }
};
</script>

<style lang="scss" scoped></style>
