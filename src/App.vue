<template>
  <q-layout view="hHh lpR fFf">
    <navbar @toggle-drawer="toggleDrawer" />
    <q-page-container>
      <carousel :items="carouselItems" />
      <div class="q-pa-md row justify-center">
        <card
          v-for="game in games"
          :key="game.id"
          :title="game.title"
          :description="game.description"
          :img-src="game.imgSrc"
          class="q-mb-md"
        />
      </div>
    </q-page-container>
    <Footer />
  </q-layout>
</template>

<script>
import { defineComponent } from 'vue';
import { QLayout, QPageContainer } from 'quasar';
import Navbar from './components/Navbar.vue';
import Carousel from './components/Carousel.vue';
import Card from './components/Card.vue';
import Footer from './components/Footer.vue';

export default defineComponent({
  name: 'App',
  components: {
    QLayout,
    QPageContainer,
    Navbar,
    Carousel,
    Card,
    Footer
  },
  data() {
    return {
      carouselItems: [
        'https://i.ibb.co/T21wJKC/image-removebg.png',
        'https://i.ibb.co/6DKrSsL/image-removebg-preview.png',
        'https://i.ibb.co/p3Sy2Rw/image-removebg-preview-1.png',
        'https://i.ibb.co/ThS5XfN/image-removebg-preview-2.png',
        'https://i.ibb.co/nLgNF68/image-removebg-preview-3.png'
      ],
      games: [
        { id: 1, title: 'ROG PHONE', description: 'Rp 18.000.000.00', imgSrc: 'https://i.ibb.co.com/k44xSyK/image-removebg-preview-4.png' },
        { id: 2, title: 'ROG MAXIMUS Z690', description: 'Rp 38.380.000.00', imgSrc: 'https://i.ibb.co.com/0YsFHrY/h525-removebg-preview.png' },
        { id: 3, title: 'ROG Strix Scope RX', description: 'Rp 1.490.000.00', imgSrc: 'https://i.ibb.co.com/Kbw3RKS/kk.png' },
        { id: 4, title: 'Playstation 5', description: 'Rp 9.909.000.00', imgSrc: 'https://i.ibb.co.com/QpRg2bh/image-removebg-preview-5.png' },
        { id: 5, title: 'Xbox Series S', description: 'Rp 5.353.400.00', imgSrc: 'https://i.ibb.co.com/0yLWnLL/image-removebg-preview-6.png' },
        { id: 6, title: 'ROG Monitor PG27AQDM', description: 'Rp 24.870.000.00', imgSrc: 'https://i.ibb.co.com/2Y132m4/image-removebg-preview-7.png' },
        { id: 7, title: 'Xiaomi Black Shark 5 Pro', description: 'Rp 14.900.000.00', imgSrc: 'https://i.ibb.co.com/k2yCX3f/image-removebg-preview-8.png' },
        { id: 7, title: 'Red Magic 7 pro', description: 'Rp 12.500.000.00', imgSrc: 'https://i.ibb.co.com/d09pP1Q/red.png' }
      ]
    };
  },
  methods: {
    toggleDrawer() {
    }
  }
});
</script>

<style>
body {
  background-color: #03070a;
  color: white;
}

.q-page-container {
  background-color: #03070a;
}

.q-card {
  background-color: #03070a;
}

.q-toolbar {
  background-color: #050d14;
}
</style>
