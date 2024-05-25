<template>
    <q-card class="game-card">
      <q-img :src="imgSrc" :alt="title" class="game-card__img"/>
      <q-card-section class="game-card__section">
        <div class="text-h6 game-card__title">{{ title }}</div>
        <div class="game-card__description">{{ description }}</div>
        <q-btn 
          color="primary" 
          icon="shopping_cart" 
          label="Purchase" 
          class="full-width game-card__btn" 
          @click="purchaseGame"
        />
      </q-card-section>
    </q-card>
  </template>
  
  <script>
  import { QCard, QImg, QCardSection, QBtn } from 'quasar';
  
  export default {
    props: {
      title: String,
      description: String,
      imgSrc: String
    },
    methods: {
      purchaseGame() {
        // Tambahkan logika untuk pembelian game
        alert(`Purchased ${this.title}`);
      }
    },
    components: {
      QCard,
      QImg,
      QCardSection,
      QBtn
    }
  }
  </script>
  
  <style scoped>
  .game-card {
    width: 300px;
    border: 2px solid;
    border-image: linear-gradient(to right, aqua, lightpink) 1;
    box-shadow: 0 0 10px aqua, 0 0 10px lightpink;
    margin: 10px;
  }
  
  .game-card__img {
    height: 250px;
  }
  
  .game-card__section {
    padding: 16px;
  }
  
  .game-card__title {
    margin-bottom: 8px;
  }
  
  .game-card__description {
    margin-bottom: 16px;
  }
  
  .game-card__btn {
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    position: sticky;
  }
  </style>
  