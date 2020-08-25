<template>
    <div class="card">
        <div class="card__container">
            <slot></slot>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@import "@/assets/scss/vars";
.card {
    width: 100%;
    max-width: 1000px;
    max-height: 500px;
    padding: 25px;
    border-radius: 25px;
    border: 1px solid $gray;
    box-shadow: 0 15px 25px rgba($text, 0.2);
    &__container {
        overflow: auto;
        max-width: 1000px;
        max-height: 500px;
    }
}
</style>
