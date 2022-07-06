<template>
  <header>
    <img src="/assets/logo.png" alt="BeerBattle Logo" id="logo" />
    <h1>BeerBattle</h1>
  </header>
</template>

<style scoped>
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
</style>
