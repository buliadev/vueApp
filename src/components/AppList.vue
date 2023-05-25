<script>
import AppCard from './AppCard.vue'

export default {
    components: {
        AppCard
    },
    props: {
        cards: Array,
    },
    data() {
        return {

        }
    },
    emits: ['finalPrice', 'finalPriceRemove'],
    methods: {

    }
}
</script>

<template>
    <div class="row row-cols-1 row-cols-md-3 g-4">
        <app-card v-for="card in cards" :key="card.id" :card="card" @final-price="$emit('finalPrice', card)" @final-price-remove="$emit('finalPriceRemove', card)"></app-card>
    </div>
</template>

<style scoped></style>
