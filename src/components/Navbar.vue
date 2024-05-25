<template>
    <q-header elevated class="bg-primary text-white">
      <q-toolbar>
        <q-btn flat round icon="menu" @click="toggleDrawer" />
        <q-toolbar-title class="title">
          <img src="https://i.ibb.co/2cL6TGp/image-removebg-preview-9.png" alt="Logo" class="logo" />
          LEXICON
        </q-toolbar-title>
        <div class="navbar-center">
          <q-btn 
            v-for="nav in navLinks" 
            :key="nav.value" 
            :label="nav.label" 
            :icon="nav.icon" 
            :value="nav.value" 
            :class="{'active-nav': activeNav === nav.value}" 
          />
        </div>
        <q-btn flat round icon="mail" class="q-ml-md" />
        <q-btn flat round icon="shopping_cart" />
      </q-toolbar>
    </q-header>
  </template>
  
  <script>
  import { QHeader, QToolbar, QBtn, QToolbarTitle } from 'quasar';
  
  export default {
    methods: {
      toggleDrawer() {
        this.$emit('toggle-drawer');
      }
    },
    data() {
      return {
        activeNav: 'produk',
        navLinks: [
          { value: 'branda', label: 'Branda', icon: 'store' },
          { value: 'produk', label: 'Produk', icon: 'shopping_bag' },
          { value: 'info', label: 'Info', icon: 'info' }
        ]
      };
    },
    components: {
      QHeader,
      QToolbar,
      QBtn,
      QToolbarTitle
    }
  };
  </script>
  
  <style scoped>
  @import url('https://fonts.googleapis.com/css2?family=Orbit&family=Pixelify+Sans:wght@400..700&family=Roboto+Mono:ital,wght@0,100..700;1,100..700&display=swap');
  
  .navbar-center {
    display: flex;
    flex: 1;
    justify-content: center;
  }
  
  .active-nav {
    border: 1px solid #fff;
  }
  
  .title {
    display: flex;
    align-items: center;
    font-family: "Roboto Mono", monospace;
    font-optical-sizing: auto;
    font-weight: bold;
    font-style: normal;
  }
  
  .logo {
    width: 60px;
    height: 60px;
    margin-right: 10px;
    filter: drop-shadow(0 0 10px rgb(7, 185, 255));
  }
  </style>
  