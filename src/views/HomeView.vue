<script setup>
import { onMounted, ref } from "vue";
import ListCharacters from "../components/ListCharacters.vue";


let characters = ref([]);

onMounted(() => {
  fetch("https://rickandmortyapi.com/api/character/")
    .then((response) => response.json())
    .then((response) => {
      characters.value = response.results;
      console.log(characters);
    });
});
</script>

<template>

<main>
  <div class="container"> 
      <ListCharacters
        v-for="character in characters"
        :key="character.id"
        :name="character.name"
        :image="character.image"
        :species="character.species"
        :status="character.status"
        :gender="character.gender"
        :location="character.location"
        :episode="character.episode"
      />
  </div>
</main>



</template>
<style>
.container{
  padding-top: 20px;
  display: flex;
  flex-wrap: wrap;
}

body{
  background-color: #1b1b53;
}


</style>
