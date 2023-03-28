<script>
import MainCards from './MainCards.vue';
export default {
    name: "AppMain",
    components: {
        MainCards
    },
}
</script>

<template>
    <div class="container-bg">
        <div class="container">
            <div class="d-flex flex-column">
                <MainCards></MainCards>
            </div>
        </div>
    </div>
</template>


<style lang="scss" scoped>
.container-bg {
    background-color: #d48f38;
    padding: 125px;

    .container {
        background-color: white;
        padding: 80px;
    }
}
</style>