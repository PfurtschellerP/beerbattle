<template>
  <Header />
  <main>
    <Game />
  </main>
  <Footer />
</template>

<script setup>
import Header from './components/Header.vue';
import Footer from './components/Footer.vue';
import Game from './components/Game.vue';
</script>

<style>
@import './css/global.css';

:root {
  --text-color: #036;
}

* {
  transition: all .1s ease;
}

body {
  height: 100vh;
  margin: 0;
  background-color: rgba(153, 204, 255, 0.2);
  background: linear-gradient(rgba(153, 204, 255, 0.2), rgba(0, 51, 102, 0.2));
  background-attachment: fixed;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: var(--text-color);
  margin: 0 6vw 0 6vw;
  height: 100%;
}

h1 {
  font-size: 1.9rem;
}

h2 {
  font-size: 1.6rem;
}
</style>
