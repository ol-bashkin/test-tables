<template>
    <input class="input" :type="type" :inputmode="inputmode" :max="max" v-model="value" @input="validateInput" />
</template>

<script>
export default {
    props: ["type", "inputmode", "max"],
    data() {
        return {
            value: "0"
        };
    },
    methods: {
        validateInput() {
            let proxyValue = this.value.replace(/[^0-9]+/g, "");
            this.value = proxyValue.slice(0, 6);
        }
    }
};
</script>

<style lang="scss" scoped>
@import "@/assets/scss/vars";
.input {
    min-width: 100px;
    padding: 0;
    border: 1px solid $gray;
    text-align: center;
    background: #fff;
    line-height: 25px;
    border-radius: 0;
}
</style>
