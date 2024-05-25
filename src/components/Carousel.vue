<template>
    <q-page class="flex flex-center">
      <div class="carousel-3d">
        <div class="carousel-3d__container">
          <div
            v-for="(item, index) in items"
            :key="index"
            class="carousel-3d__item"
            :class="{ 'selected': selectedIndex === index }"
            @click="selectItem(index)"
          >
            <img :src="item" alt="Image" />
          </div>
        </div>
        <div class="carousel-3d__dots">
          <div
            v-for="(item, index) in items"
            :key="index"
            class="carousel-3d__dot"
            :class="{ 'active': selectedIndex === index }"
            @click="selectItem(index)"
          ></div>
        </div>
      </div>
      <div class="carousel-3d__text">
        <div class="no-background">
          <span class="text-h3">
            "Game on, conquer <br>the unknown <br>Quest for victory"
          </span>
        </div>
      </div>
    </q-page>
  </template>
  
  <script>
  import { QPage } from 'quasar';
  
  export default {
    props: {
      items: {
        type: Array,
        required: true
      }
    },
    data() {
      return {
        selectedIndex: 0
      };
    },
    methods: {
      selectItem(index) {
        this.selectedIndex = index;
      }
    },
    components: {
      QPage
    }
  }
  </script>
  
  <style scoped>
  @import url('https://fonts.googleapis.com/css2?family=Orbit&display=swap');
  @import url('https://fonts.googleapis.com/css2?family=Orbit&family=Pixelify+Sans:wght@400..700&display=swap');

  .carousel-3d {
    perspective: 1000px;
    width: 100%;
    height: 400px;
    position: relative;
    display: flex;
    align-items: center;
  }
  
  .carousel-3d__container {
    position: relative;
    width: 50%;
    height: 100%;
    transform-style: preserve-3d;
    animation: rotate 10s infinite linear;
  }
  
  .carousel-3d__item {
    width: 270px;
    height: 300px;
    margin: 10px;
    position: absolute;
    top: 50%;
    left: 50%;
    transform-origin: center center;
    transform-style: preserve-3d;
    transition: transform 0.3s ease-in-out, opacity 0.3s ease-in-out;
    mix-blend-mode: darken;
    filter: drop-shadow(0 0 30px rgb(128, 170, 244));
  }
  
  .carousel-3d__item img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
  
  .carousel-3d__item.selected {
    animation: none;
    transform: translate(-50%, -50%) !important;
    z-index: 10;
  }
  
  .carousel-3d__item:not(.selected) {
    transform: rotateY(0deg) translateZ(400px) translateX(-50%) translateY(-50%);
    z-index: 5;
    opacity: 0;
    pointer-events: none;
  }
  
  .carousel-3d__dot {
    width: 12px;
    height: 12px;
    background-color: rgba(29, 29, 29, 0.5);
    border-radius: 50%;
    margin: 0 5px;
    cursor: pointer;
    transition: background-color 0.3s ease;
  }
  
  .carousel-3d__dot.active {
    background-color: rgb(39, 38, 38);
  }
  
  .carousel-3d__dots {
    position: absolute;
    bottom: -10px;
    left: 50%;
    transform: translateX(-50%);
    display: flex;
    justify-content: center;
    align-items: center;
  }
  
  .carousel-3d__text {
    position: absolute;
    right: 200px;
    top: 50%;
    transform: translateY(-50%);
    max-width: 100%;
    text-align: center;
  }
  
  .no-background {
    background: none !important;
  }
  
  .text-h3 {
  font-size: 48px;
  font-family: "Pixelify Sans", sans-serif;
  text-shadow: 0 0 30px rgb(129, 209, 249);
  background: linear-gradient(90deg, red, orange, yellow, green, cyan, blue, violet);
  background-clip: text;
  -webkit-background-clip: text;
  color: transparent;
  font-style: italic; /* Membuat teks miring */
}

  </style>
  