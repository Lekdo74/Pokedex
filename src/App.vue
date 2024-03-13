<script setup>

</script>

<template>
  <router-link to="/">
    <h1 class="title">Pokédex</h1>
  </router-link>

  <router-view></router-view>
</template>

<style scoped>
.title{
  display:inline-block;
  position: relative;
  left: 50%;
  transform: translateX(-50%);
  margin-top: -2rem;
  margin-bottom: -1rem;
  text-decoration: none;
  color: black;
  font-family: pokemonFont;
  letter-spacing: 0.5rem;
  font-size: 5rem;
  transition: all 0.3s ease-in-out;
}

.title:hover{
  transform: translateX(-50%) scale(1.05);
}

@font-face {
  font-family: pokemonFont;
  src: url('./assets/fonts/Pokemon_Solid.ttf');
}
</style>
