<script setup>
defineProps({
  name : String
});
</script>

<template>
    <img class="imageType" v-bind:src="'https://veekun.com/dex/media/types/en/' + name + '.png'">
</template>

<style scoped>
    .imageType{
        image-rendering: crisp-edges;
        transform: scale(2);
        margin: 20px 20px 0px 20px;
    }
</style>