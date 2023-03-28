<script>
export default {
    name: "Card",
    props: {
        img: String,
        name: String,
        archetype: String
    }
}
</script>

<template>
    <article class="h-100">
        <img :src="img" :alt="name">
        <h2>{{ name.toUpperCase() }}</h2>
        <h3>{{ archetype }}</h3>
    </article>
</template>



<style lang="scss" scoped>
article {
    background-color: #d48f38;
    text-align: center;

    img {
        width: 100%;
    }

    h2,
    h3 {
        padding: 10px;
    }

    h2 {
        color: white;
        font-size: 20px;

    }

    h3 {
        font-size: 17px;
    }

}
</style>