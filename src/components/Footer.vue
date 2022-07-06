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
  text-align: center;
  font-size: x-small;
  color: black;
  user-select: none;
  padding: 1rem 0;
  color: gray;
}

footer p {
  margin: 0;
}
</style>
