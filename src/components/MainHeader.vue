<script>
import { store } from '../store';
export default {
    name: "MainHeader",
    data() {
        return {
            store
        }
    },
}
</script>

<template>
    <div class="col-12 main-header">
        <div>Found {{ store.cardsNumber }} cards</div>
    </div>
</template>



<style lang="scss" scoped>
.main-header {
    background-color: #212529;
    padding: 15px 40px;

    div {
        color: white;
    }
}
</style>