<template>
  <div>
    <footer>
      <p>&copy;{{ new Date().getFullYear() }} by a group of DHBW Students</p>
    </footer>
  </div>
</template>

<script setup>

</script>

<style scoped>
footer {
  position: fixed;
  bottom: 1rem;
  left: 50%;
  transform: translateX(-50%);
  font-size: x-small;
  color: lightgray;
  user-select: none;
}

footer p {
  margin: 0;
}
</style>
