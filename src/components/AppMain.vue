<script>
import MainHeader from './MainHeader.vue';
import MainCards from './MainCards.vue';
export default {
    name: "AppMain",
    components: {
        MainHeader,
        MainCards
    },
}
</script>

<template>
    <div class="container-bg">
        <div class="container">
            <div class="d-flex flex-column">
                <MainHeader></MainHeader>
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