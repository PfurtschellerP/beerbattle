<template>
  <div class="main">
    <div class="game">
      <div class="beerA beer">
        <img src="https://static.hanos.com/sys-master/productimages/h37/hfe/9755509850142/01111675_lev.jpg_256Wx256H"
          alt="Beer A" />
        <h3>{{ beerA.name }}</h3>
      </div>
      <div class="beerB beer">
        <img src="https://static.hanos.com/sys-master/productimages/h5a/hfd/9639302529054/01400360_lev.jpg_256Wx256H"
          alt="Beer B" />
        <h3>{{ beerB.name }}</h3>
      </div>
    </div>
    <div class="description">
      <p>Get your beer from the tap and decide which one you prefer.</p>
      <p>This round is between {{ beerA.name }} and {{ beerB.name }}.</p>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const beerA = ref({
  name: "La Chouffe"
})
const beerB = ref({
  name: "San Miguel"
})
</script>

<style scoped>
.main {
  display: flex;
  flex-direction: column;
}

.game {
  display: flex;
  justify-content: space-between;
}

img {
  width: 100%;
  border-radius: 1rem;
  mix-blend-mode: multiply;
}

.beer {
  flex: 1;
  /* border: 1px solid red; */
  box-shadow: 0px 2px 10px -8px rgba(0, 0, 0, .7);
  border-radius: 1rem;
  text-align: center;
  padding: 1rem 0;
}

.description {
  text-align: center;
}

h3 {
  padding: 0;
  margin: 0;
}
</style>
