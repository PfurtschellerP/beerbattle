<template>
  <header>
    <img class="hamburger clickable" src="/assets/hamburger.svg" @click="toggleMenu()" alt="≡" />
    <Transition>
      <Menu class="menu" v-if="showMenu" @close-me="showMenu = false" />
    </Transition>
    <img src="/assets/logo.png" alt="BeerBattle Logo" id="logo" />
    <h1>BeerBattle</h1>
  </header>
</template>

<script setup>
import { ref } from 'vue';
import Menu from './Menu.vue';

const showMenu = ref(false)

const toggleMenu = () => showMenu.value = !showMenu.value
</script>

<style scoped>
.hamburger {
  position: absolute;
  top: 3vw;
  right: 3vw;
}

.menu {
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  z-index: 2022;
}

header {
  text-align: center;
}

nav {
  display: flex;
  flex-flow: row-nowrap;
}

#logo {
  width: 8rem;
  margin-top: 5vh;
}

ul {
  display: flex;
  list-style: none;
  padding: 0;
  margin: 0 auto;
}

li {
  padding: .5em;
  flex: 1;
  text-align: center;
}

nav a {
  color: inherit;
  text-decoration: none;
}

a:hover {
  text-decoration: underline;
}

/* Vue Fade Transition */
.v-enter-active,
.v-leave-active {
  transition: opacity 0.3s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}
</style>
