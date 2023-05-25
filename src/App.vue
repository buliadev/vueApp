<script>
import AppList from './components/AppList.vue'

export default {
  components: {
    AppList
  },
  data() {
    return {
      finalPrice: 0,
      cards: [
        {
          id: 1,
          name: 'Jija1',
          price: 300,
          description: 'Jija tovar imba',
          img: 'src/assets/present.jpg',
          count: 0
        },
        {
          id: 2,
          name: 'Jija2',
          price: 400,
          description: 'Jija tovar imba',
          img: 'src/assets/present.jpg',
          count: 0
        },
        {
          id: 3,
          name: 'Jija3',
          price: 500,
          description: 'Jija tovar imba',
          img: 'https://i.ytimg.com/vi/caG12-6VM0c/maxresdefault.jpg',
          count: 0
        },
        {
          id: 4,
          name: 'Jija4',
          price: 100,
          description: 'Jija tovar imba',
          img: 'src/assets/present.jpg',
          count: 0
        },
    ]
    }
  },
  methods: {
      FinalPrice(card) {
            this.finalPrice += card.price;
            this.cards[this.cards.indexOf(card)].count++;
      },
      FinalPriceRemove(card) {
            this.finalPrice -= card.price;
            this.cards[this.cards.indexOf(card)].count--;
        }
    }
}
</script>

<template>
  <header>
    <div class="wrapper">
      <h1>Товаров в корзине на сумму: {{ finalPrice }}р.</h1>  
      <app-list :cards="cards"  @final-price="FinalPrice" @final-price-remove="FinalPriceRemove"></app-list>
    </div>
  </header>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
