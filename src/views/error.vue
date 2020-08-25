<template>
    <main class="error">
        <div class="error__container">
            <p class="error__code">404</p>
            <h1 class="error__title">Страница не&nbsp;найдена</h1>
        </div>
    </main>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@import "@/assets/scss/vars";
.error {
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: left;
    height: 100%;
    &__container {
        max-width: 66%;
    }
    &__code {
        margin: 0 0 8px;
        font-weight: bold;
        font-size: 24px;
        color: $primary;
    }
    &__title {
        margin: 0;
    }
}
</style>
