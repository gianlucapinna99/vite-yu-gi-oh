<script>
import Card from './Card.vue';
import { store } from '../store';
export default {
    name: "MainCards",
    components: {
        Card
    },
    data() {
        return {
            store
        }
    },
}
</script>

<template>
    <div class="col-12">
        <div class="row">
            <div v-for="(card, index) in store.cards" class="col-3 mb-3">
                <template v-if="index < 100">
                    <Card :img="card.card_images[0].image_url" :name="card.name" :archetype="card.archetype">
                    </Card>
                </template>
            </div>
        </div>
    </div>
</template>



<style lang="scss" scoped></style>
