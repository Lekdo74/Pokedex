<script setup>
import Type from '../components/Type.vue'

defineProps({
  name : String,
  id : Number,
  types : {
        type: Array,
        default: () => []
    },
  height : Number,
  weight : Number,
  hp : Number,
  attack : Number,
  defense : Number,
  speed : Number
});

</script>

<template>
  <table>
    <tr class="imageRow">
      <td colspan="2">
        <img class="pokemonImage" v-bind:src="'https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/home/' + id + '.png'">
      </td>
    </tr>
    <tr class="nameRow">
      <td colspan="2">
        <div class="name">
          {{ name[0].toUpperCase() + name.slice(1) }}
        </div>
      </td>
    </tr>
    <tr class="statsRow">
      <td>
        <tr class="typesRow">
          <tr class="typesWordRow stat">Types :</tr>
          <tr class="typesImagesRow">
            <td class ="typesImageColumn">
              <Type v-for="typ of types"
              :name="typ.type['name']">
              </Type>
            </td>
          </tr>
        </tr>
        <tr class="heightWeightRow">
          <td class="heightColumn"><tr class="heightRow stat">Height : {{ height / 10 }} m</tr></td>
          <td class="weightColumn"><tr class="weightRow stat">Weight : {{ weight / 10 }} kg</tr></td>
        </tr>
      </td>
      <td>
        <tr class="hpRow stat">Hp : {{ hp }}</tr>
        <tr class="attackRow stat">Attack : {{ attack }}</tr>
        <tr class="defenseRow stat">Defense : {{ defense }}</tr>
        <tr class="speedRow stat">Speed : {{ speed }}</tr>
      </td>
    </tr>
  </table>
</template>

<style scoped>
table{
  min-width: 300px;
  width: 40vw;
  margin-left: auto;
  margin-right: auto;
  min-height: 600px;
  height: 80vh;
  background-color:darkslategray;
  border: black solid 5px;
  border-radius: 50px;
}

.imageRow{
  height: 33%;
}

.nameRow{
  height: 17%;
}

.statsRow{
  height: 50%;
}

.typesHeightWeightRows{
  height: 50%;
}

.typesRow{
  position: absolute;
  width: 100%;
  top: 0%;
  height: 50%;
}

.typesWordRow{
  position: absolute;
  left: 50%;
  top: 25%;
  transform: translate(-50%, -50%);
}

.typesImagesRow{
  position: absolute;
  width: 100%;
  top: 35%;
  height: 65%;
}

.typesImageColumn{
  width: auto;
  position: absolute;
  left: 50%;
  top: 0%;
  transform: translate(-50%, 0%);
}

.heightWeightRow{
  position: absolute;
  width: 100%;
  top: 50%;
  height: 50%;
}

.heightColumn{
  position: absolute;
  height: 100%;
  left: 0%;
  width: 50%;
}

.weightColumn{
  position: absolute;
  height: 100%;
  left: 50%;
  width: 50%;
}

.heightRow{
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
}

.weightRow{
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
}

.hpRow{
  position: absolute;
  left: 50%;
  top: 20%;
  transform: translate(-50%, -50%);
}

.attackRow{
  position: absolute;
  left: 50%;
  top: 40%;
  transform: translate(-50%, -50%);
}

.defenseRow{
  position: absolute;
  left: 50%;
  top: 60%;
  transform: translate(-50%, -50%);
}

.speedRow{
  position: absolute;
  left: 50%;
  top: 80%;
  transform: translate(-50%, -50%);
}

td{
  width: 50%;
  position: relative;
}

.pokemonImage{
  height: 130%;
  position: absolute;
  top: -30px;
  left: 50%;
  transform: translateX(-50%);
}

.name{
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
  color: white;
  font-size: 3rem;
}

.stat{
  color: white;
  font-size: 1.5rem;
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