<template>
  <div class="game">
    <div class="beerA">
      <img
        src="https://th.bing.com/th/id/R.7f3e661653e3e7d9e14eb63d3a4bf16f?rik=ijn6%2f2QYDutfpw&pid=ImgRaw&r=0"
        alt="Beer A"
      />
      <h3>Beer A</h3>
    </div>
    <h2>Or</h2>
    <div class="beerB">
      <img
        src="https://th.bing.com/th/id/R.2b4a5b8e76bcae6dfa573a91787fb02c?rik=UliQxhLS6Ee%2bFA&pid=ImgRaw&r=0"
        alt="Beer B"
      />
      <h3>Beer B</h3>
    </div>
  </div>
</template>

<style scoped>
  .game {
    display: grid;
    grid-template-columns: 2fr 1fr 2fr;
    grid-template-rows: 1fr;
    grid-column-gap: 0px;
    grid-row-gap: 0px;
  }

  img {
    height: 20vh;
  }

  h2 {
    line-height: 20vh;
    vertical-align: center;
  }
</style>
