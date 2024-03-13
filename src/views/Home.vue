<script setup>
import { ref, onMounted } from 'vue'
import PokemonBox from '../components/PokemonBox.vue'

const data = ref();

async function fetchAPI(){
  fetch('https://pokeapi.co/api/v2/pokemon?offset=0&limit=100').then((response) => response.json()).then((responseJson) => {
    data.value = responseJson;
  }).catch((error) => {
    console.log(error);
  })
}

onMounted(fetchAPI);
</script>

<template>
    <div align="center" v-if="data?.results">
        <PokemonBox v-for="pokemon of data.results"
            :name="pokemon.name"
            :url="pokemon.url">
        </PokemonBox>
    </div>
</template>

<style scoped>

</style>
