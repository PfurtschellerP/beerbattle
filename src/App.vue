<script setup>
  import Header from './components/Header.vue';
  import Footer from './components/Footer.vue';
  import Game from './components/Game.vue';
</script>

<template>
  <Header />
  <main>
    <Game />
  </main>
  <Footer />
</template>

<style>
  :root {
    --text-color: black;
  }

  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    margin: 0 10vw 0;
  }

  h1 {
    font-size: 1.9em;
  }

  h2 {
    font-size: 1.6em;
  }
</style>
