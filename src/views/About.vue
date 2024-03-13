<script setup>
import { ref, onMounted } from 'vue'
import PokemonAbout from '../components/PokemonAbout.vue'

const data = ref();

async function fetchAPI(){
    let url = window.location.href;

    fetch('https://pokeapi.co/api/v2/pokemon/' + url.slice(url.slice(0, -1).lastIndexOf('/') + 1)).then((response) => response.json()).then((responseJson) => {
        data.value = responseJson;
    }).catch((error) => {
        console.log(error);
    })
}

onMounted(fetchAPI);
</script>

<template>
    <div v-if="data!=null">
        <PokemonAbout
        :name="data.name"
        :id="data.id"
        :types="data.types"
        :height="data.height"
        :weight="data.weight"
        :hp="data['stats']['0']['base_stat']"
        :attack="data['stats']['1']['base_stat']"
        :defense="data['stats']['2']['base_stat']"
        :speed="data['stats']['5']['base_stat']"
        >
        </PokemonAbout>
    </div>
</template>

<style scoped>

</style>
