<script setup>
const personagem = defineProps(["name", "url", "status", "specie", "gender", "location", "episode"])
const personagemId = personagem.url.split('/')[5]
const imageUrl = "https://rickandmortyapi.com/api/character/avatar/" + personagemId + ".jpeg"
console.log(imageUrl)

</script>

<template>
    <div class="col-md-3">
        <div class="card p-2 mb-3">
            <img :src="imageUrl" alt="">
            <p class="text-center"><strong>Nome:</strong>  {{personagem.name}}</p>
            <p class="text-center"><strong>Status:</strong>  {{personagem.status}}</p>
            <p class="text-center"><strong>Especie:</strong>  {{personagem.specie}}</p>
            <p class="text-center"><strong>Gênero:</strong>  {{personagem.gender}}</p>
            <p class="text-center"><strong>Localização Atual:</strong> {{personagem.location}}</p>
            <p class="text-center"> <strong>Aparições:</strong> {{personagem.episode.length}}</p>
        </div>
    </div>
</template>

<style>

</style>