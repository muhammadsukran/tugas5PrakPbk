<template>
    <q-footer class="text-center bg-dark text-white">
      <q-toolbar>
        <q-toolbar-title>
          &copy; Copyright 2024 <br>
          Mhdsukran
        </q-toolbar-title>
      </q-toolbar>
    </q-footer>
  </template>
  
  <script>
  import { defineComponent } from 'vue';
  import { QFooter, QToolbar, QToolbarTitle } from 'quasar';
  
  export default {
    components: {
      QFooter,
      QToolbar,
      QToolbarTitle
    }
  }
  </script>

  