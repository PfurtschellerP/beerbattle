<template>
  <div>
    <div class="backdrop" @click="emit('closeMe')" />
    <div class="content">
      <ul>
        <li v-for="beer in beers">{{ beer.name }}</li>
      </ul>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const emit = defineEmits(['closeMe'])

const beers = ref([
  {
    name: 'Welde Bourbon Barrel',
    img: '/assets/beers/welde.jpg',
    rating: 621,
    votes: 0,
  },
  {
    name: 'Kehrwieder Solero IPA',
    img: '/assets/beers/solero.jpg',
    rating: 187,
    votes: 0,
  },
  {
    name: 'Kehrwieder Imperial Stout',
    img: '/assets/beers/kentucky.jpg',
    rating: 218,
    votes: 0,
  },
  {
    name: 'BrewDog Punk IPA',
    img: '/assets/beers/punk.jpg',
    rating: 483,
    votes: 0,
  },
  {
    name: 'Winterhuder Helles',
    img: '/assets/beers/winterhuder.jpg',
    rating: 349,
    votes: 0,
  },
  {
    name: 'Craftwerk New England',
    img: '/assets/beers/craftwerk.jpg',
    rating: 192,
    votes: 0,
  },
  {
    name: 'Maisel & Friends BrewBQ',
    img: '/assets/beers/brewbq.jpg',
    rating: 510,
    votes: 0,
  },
]);
</script>

<style scoped>
.backdrop {
  z-index: 2000;
  width: 200vw;
  height: 200vh;
  background: rgba(0, 0, 0, .3);
}

.content {
  padding: 10vw;
  border-radius: 1rem;
  background: whitesmoke;
  filter: brightness(120%);
  z-index: 2022;
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
}

ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
}

li {
  font: 200 20px/1.5 Helvetica, Verdana, sans-serif;
  border-bottom: 1px solid #336699;
}

li:last-child {
  border: none;
}
</style>