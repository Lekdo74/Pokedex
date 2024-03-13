<script setup>
defineProps({
  name : String,
  url : String
});

</script>

<template>
  <router-link :to="{ name: 'About', params: { id: url.slice(url.slice(0, -1).lastIndexOf('/') + 1, -1) }}">
    <div class="pokemonBox">
      <img class="pokemonImage" v-bind:src="'https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/home/' + url.slice(url.slice(0, -1).lastIndexOf('/') + 1, -1) + '.png'">
      <p class="pokemonName">{{ name[0].toUpperCase() + name.slice(1) }}</p>
    </div>
  </router-link>
</template>

<style scoped>
.pokemonBox{
  margin: 20px;
  width: 300px;
  height: 300px;
  border-radius: 50px;
  border: black solid 5px;
  background-color:darkslategray;
  display: inline-block;
  transition: all 0.3s ease-in-out;
  position:relative;
}

.pokemonBox:hover{
  transform: scale(1.05);
}

.pokemonImage{
  position: absolute;
  top: 8%;
  left: 50%;
  transform: translate(-50%, 0%);
  height: 200px;
}

.pokemonName{
  position: absolute;
  bottom: -10px;
  left: 50%;
  transform: translate(-50%, 0%);
  font-size: 1.5rem;
  color: white;
}
</style>