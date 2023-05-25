<script>
import AppButtonCart from './AppButtonCart.vue'
import AppButtonAdd from './AppButtonAdd.vue'
import AppButtonRemove from './AppButtonRemove.vue'

export default {
    components: {
        AppButtonCart,
        AppButtonAdd,
        AppButtonRemove
    },
    props: {
        card: Object,
    },
    methods: {
        
    },
    emits: ['finalPrice', 'finalPriceRemove'],
}
</script>

<template>
    <div class="col">
        <div class="card h-100">
            <img :src="card.img" class="card-img-top" alt="...">
            <div class="card-body">
                <h5 class="card-title">{{ card.name }}</h5>
                <p class="card-text">{{ card.description }}</p>
                <p class="card-text">Цена: {{ card.price }}р.</p>
                <app-button-cart  v-if="!card.count" @click="$emit('finalPrice')"></app-button-cart> 
                <div class="btn-group btn-group-lg justify-content-center" v-if="card.count" >
                    <app-button-add @click="$emit('finalPrice')"></app-button-add>
                    <app-button-remove @click="$emit('finalPriceRemove')"></app-button-remove>
                </div> 
                <div v-if="card.count">В корзине: {{ card.count }} шт.</div>
            </div>
        </div>
    </div>
</template>

<style scoped></style>
