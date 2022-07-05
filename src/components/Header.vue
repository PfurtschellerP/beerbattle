<template>
  <nav>
    <img src="/assets/logo.png" alt="" />
    <h1>BeerBattle</h1>
    <ul>
      <a href="#"><li>The idea</li></a>
      <a href="#"><li>How it works</li></a>
      <a href="#"><li>Menu</li></a>
    </ul>
  </nav>
</template>

<style scoped>
  nav {
    display: flex;
    flex-flow: row-nowrap;
    height: 10vh;
    border-bottom: 1px solid rgba(0, 0, 0, 0.2);
  }

  img {
    margin-right: 0.4rem;
  }

  ul {
    display: flex;
    flex-flow: row nowrap;
    list-style: none;
  }

  li {
    padding: 1.5em;
  }

  a {
    color: var(--text-color);
    text-decoration: none;
  }

  a:hover {
    text-decoration: underline;
  }
</style>
