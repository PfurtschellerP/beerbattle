<template>
  <div class="main">
    <div class="game">
      <div class="beerA beer clickable" @click="vote('0')">
        <img :src="beers[0].img" alt="Beer A" />
        <h3>{{ beers[0].name }}</h3>
        <!-- <p class="rating">Rating: {{ beers[0].rating }}</p> -->
      </div>

      <div class="seperator-father">
        <h2 class="seperator">VS</h2>
      </div>

      <div class="beerB beer clickable" @click="vote('1')">
        <img :src="beers[1].img" alt="Beer B" />
        <h3>{{ beers[1].name }}</h3>
        <!-- <p class="rating">Rating: {{ beers[1].rating }}</p> -->
      </div>
    </div>

    <div class="description">
      <p>Get your beer from the tap and decide which one you prefer.</p>
      <p>This round is between {{ beers[0].name }} and {{ beers[1].name }}.</p>
    </div>

    <div class="leaderboard">
      <h3>Leaderboard</h3>
      <table>
        <tr class="tableHeader">
          <th>Name</th>
          <th>Rating</th>
          <th>Votes</th>
        </tr>
        <tr v-for="record in data" :key="record.name">
          <td>{{ record.name }}</td>
          <td>{{ record.rating }}</td>
          <td>{{ record.votes }}</td>
        </tr>
      </table>
    </div>

    <!-- <section class="debug">
    <h2>Debug</h2>
    <p>{{ JSON.stringify(data) }}</p>
  </section> -->
  </div>
</template>

<script setup>
import { reactive, onMounted, computed } from 'vue';
import EloRating from 'elo-rating';

const data = reactive([
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

const beers = reactive([
  {
    name: 'Loading',
    img: '/assets/beers/bitburger.jpeg',
    rating: 0,
    votes: 0,
  },
  {
    name: 'Loading',
    img: '/assets/beers/heineken.png',
    rating: 0,
    votes: 0,
  },
]);
var beerAIndex = 0;
var beerBIndex = 0;

function getRandomInt(max) {
  return Math.floor(Math.random() * max);
}

const sortLeaderboard = () => {
  data.values = data.sort((a, b) => {
    return a.rating < b.rating ? 1 : -1;
  });
};

const shuffleBeers = () => {
  // draw two random beers
  beerAIndex = getRandomInt(data.length);
  beerBIndex = getRandomInt(data.length);

  while (beerAIndex == beerBIndex) beerBIndex = getRandomInt(data.length);

  beers[0] = data[beerAIndex];
  beers[1] = data[beerBIndex];

  sortLeaderboard();
};
onMounted(shuffleBeers);

const vote = async (beer) => {
  const ratingA = parseFloat(beers[0].rating);
  const ratingB = parseFloat(beers[1].rating);

  const aWins = beer == '0' ? true : false;

  const result = EloRating.calculate(beers[0].rating, beers[1].rating, aWins);

  data[beerAIndex].rating = result.playerRating;
  data[beerBIndex].rating = result.opponentRating;
  data[beerAIndex].votes++;
  data[beerBIndex].votes++;
  shuffleBeers();
};

const leaderboard = computed((data) => {
  return _.orderBy(this.data, 'rating');
});
</script>

<style scoped>
table {
  border-collapse: collapse;
  width: 100%;
  margin: 25px 0;
  font-size: 0.9em;
  font-family: sans-serif;
  box-shadow: 0 0 10px -2px rgba(0, 0, 0, 0.15);
}

tr {
  background-color: #336699;
  color: #ffffff;
  text-align: left;
  cursor: crosshair;
}

tr:hover {
  filter: brightness(95%);
}

th {
  background-color: rgba(0, 0, 0, 0.1);
  padding: 12px 15px;
}

td {
  border-top: 1px solid black;
  background-color: rgba(0, 0, 0, 0.02);
  padding: 12px 15px;
}

.main {
  display: flex;
  flex-direction: column;
}

.game {
  display: flex;
  justify-content: space-between;
}

img {
  height: 30vw;
  border-radius: 1rem 1rem 0 0;
  mix-blend-mode: multiply;
}

.beer {
  flex: 1;
  box-shadow: 0px 2px 10px -8px rgba(0, 0, 0, .7);
  border-radius: 1rem;
  text-align: center;
  padding: 1rem 0;
  background-color: white;
}

.beer h3 {
  padding: 0 1vw;
}

.description {
  text-align: center;
}

.leaderboard h3 {
  padding: 0;
  margin: 0;
}

.seperator-father {
  display: flex;
  flex-direction: column;
  justify-content: center;
}

h2.seperator {
  color: darkred;
  font-weight: bolder;
  padding: 2vw;
}

.leaderboard h3, table {
  margin: 0;
}

h3,
.rating {
  padding: 0;
  margin: 0;
}
</style>
