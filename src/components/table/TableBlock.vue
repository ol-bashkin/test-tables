<template>
    <table class="table">
        <TableHeader :headers="options.headers" :current="options.current" />
        <TableBody :tbody="options.tbody" :component="options.component" :current="options.current" />
    </table>
</template>

<script>
import TableHeader from "./TableHeader.vue";
import TableBody from "./TableBody.vue";
export default {
    components: {
        TableHeader,
        TableBody
    },
    props: {
        options: {
            type: Object,
            required: true
        }
    }
};
</script>

<style lang="scss" scoped>
.table {
    border-collapse: collapse;
}
</style>
