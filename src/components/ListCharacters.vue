<script setup>

import { defineProps } from "vue";

const character = defineProps([
  "name",
  "image",
  "species",
  "status",
  "gender",
  "location",
  "episode",
]);
const episodeCount = character.episode.length;



</script>

<template>
<main>
  <div class="container" style="max-width: 19rem; flex: auto; flex-wrap: wrap; display: flex;">
    <div class="card border-card mb-3">
       <img class="img" :src="character.image" alt="..." />
       <div class="card-body">
        <p class="card-text"><strong>Nome: </strong>{{ character.name }}</p>
        <p class="card-text"><strong>Especie: </strong>{{ character.species }}</p>
        <p class="card-text"><strong>Status: </strong>{{ character.status }}</p>
        <p class="card-text"><strong>Genero: </strong>{{ character.gender }}</p>
        <p class="card-text"><strong>Localização Atual: </strong>{{ character.location.name }}</p>
        <p class="card-text"><strong>Número de episódios: </strong> {{ episodeCount }}</p>
      </div>
      </div>
    </div>
</main>


</template>


<style>
.card{
  background-color: #222267;
  text-align: center;
}
.card-text{

  color: #ffff74;
}


.card-wrapper {
  flex: 0 0 19rem; 
  margin-right: 1rem; 
}


</style>
