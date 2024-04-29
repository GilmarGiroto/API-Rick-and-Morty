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
            <p class="text-center"> Nome: {{personagem.name}}</p>
            <p class="text-center"> Status: {{personagem.status}}</p>
            <p class="text-center"> Especie: {{personagem.specie}}</p>
            <p class="text-center"> Gênero: {{personagem.gender}}</p>
            <p class="text-center">Localização Atual: {{personagem.location}}</p>
            <p class="text-center"> Episódio: {{personagem.episode}}</p>
        </div>
    </div>
</template>

<style>

</style>