<script>
import Card from './Card.vue';
import { store } from '../store';
import MainHeader from './MainHeader.vue';

export default {
    name: "MainCards",
    components: {
        Card,
        MainHeader
    },
    data() {
        return {
            store,
            selectedArchetype: ''
        }
    },
    computed: {
        archetypes() {
            // crea un array di tutti gli archetipi
            return [...new Set(this.store.cards.map(card => card.archetype))];
        },
        filteredCards() {
            if (this.selectedArchetype) {
                // filtra le carte per archetipo
                return this.store.cards.filter(card => card.archetype === this.selectedArchetype);
            } else {
                // mostra tutte le carte se nessun archetipo è selezionato
                return this.store.cards;
            }
        }
    }
}
</script>


<template>
    <div class="col-12">
        <div class="row">
            <div class="col-12 mb-3 mt-3">
                <select id="archetype-select" v-model="selectedArchetype">
                    <option value="">Seleziona archetipo</option>
                    <option v-for="archetype in archetypes" :key="archetype" :value="archetype">{{ archetype }}</option>
                </select>
            </div>
            <MainHeader class="main-header"></MainHeader>
            <div v-for="(card, index) in filteredCards" class="col-3 mb-3">
                <template v-if="index < 100">
                    <Card :img="card.card_images[0].image_url" :name="card.name" :archetype="card.archetype">
                    </Card>
                </template>
            </div>
        </div>
    </div>
</template>


<style lang="scss" scoped>
.main-header {
    width: calc(100% - 30px);
    margin: 0 auto;
}
</style>